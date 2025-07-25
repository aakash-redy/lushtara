# Lushtara
# Lushtára

Lashtára is an AI-integrated food translation and recommendation system designed to assist travelers in navigating unfamiliar culinary environments. The application analyzes physical menus and uses user-defined preferences to generate ranked food suggestions based on a proprietary scoring system.

## Core Functionality

Lashtára supports users by performing the following:

- Scans and translates physical food menus in any supported language.
- Accepts five personalized preference inputs:
  - Taste
  - Weather conditions
  - Mood
  - Budget constraints
  - Portion size

- Filters menu items and ranks them based on a scoring metric called **Cravins**, which represents the degree of alignment between a dish and the user's stated preferences.

## Cravins Scoring System

Each dish receives a **Cravins** score ranging from +5 to -5:

- **+5** indicates highest resonance with user preferences.
- **0** represents neutral or moderate match.
- **-5** reflects least alignment.

All menu items are listed in descending order of Cravins, enabling users to make informed decisions.

## Technical Summary

- Computer vision and OCR for menu scanning.
- Language translation APIs to interpret text.
- AI-driven filtering based on weighted preference logic.
- Responsive interface optimized for travel conditions and low-bandwidth environments.

## Use Case Scenario

Lashtára is intended for international travelers who may face linguistic and cultural barriers when selecting food. By offering personalized, preference-aligned suggestions, the system reduces uncertainty and improves decision efficiency.

## Repository Structure


## License

This repository is currently under evaluation for licensing. No redistribution or modification rights are granted unless explicitly stated.

## Contact

For collaboration, technical queries, or documentation access, reach out via the GitHub Issues section.


---
import java.util.*;

public class LashtaraCore {

    static class Food {
        String name, taste, texture, temp, mood, portion;
        int price;
        int cravins = 0;

        Food(String name, String taste, String texture, String temp, String mood, int price, String portion) {
            this.name = name;
            this.taste = taste;
            this.texture = texture;
            this.temp = temp;
            this.mood = mood;
            this.price = price;
            this.portion = portion;
        }
    }

    static List<String> cravingMemory = new ArrayList<>();

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // 🔘 Dish Pool
        List<Food> pool = new ArrayList<>(List.of(
                new Food("Cone Ice Cream", "sweet", "crunchy", "cold", "celebration", 45, "small"),
                new Food("Samosa", "spicy", "crunchy", "hot", "comfort", 25, "small"),
                new Food("Pulihora", "tangy", "soft", "mid", "stress", 30, "medium"),
                new Food("Gulab Jamun", "sweet", "soft", "hot", "comfort", 40, "small"),
                new Food("Dhokla", "savory", "soft", "mid", "celebration", 35, "medium"),
                new Food("Fruit Salad", "sweet", "soft", "cold", "stress", 30, "medium")
        ));

        // 🎭 Craving Input Ritual
        Map<String, Integer> moodMap = Map.of("comfort", 1, "celebration", 2, "stress", 3);
        Map<String, Integer> tasteMap = Map.of("sweet", 1, "spicy", 2, "tangy", 3, "savory", 4);
        Map<String, Integer> textureMap = Map.of("crunchy", 1, "soft", 2);
        Map<String, Integer> tempMap = Map.of("cold", 1, "mid", 2, "hot", 3);
        Map<String, Integer> portionMap = Map.of("small", 1, "medium", 2, "large", 3);

        System.out.println("\n🌿 Enter your craving inputs:");

        System.out.println("Select Mood:\n1. comfort\n2. celebration\n3. stress");
        int moodInput = scanner.nextInt();

        System.out.println("Select Taste:\n1. sweet\n2. spicy\n3. tangy\n4. savory");
        int tasteInput = scanner.nextInt();

        System.out.println("Select Texture:\n1. crunchy\n2. soft");
        int textureInput = scanner.nextInt();

        System.out.println("Select Temperature:\n1. cold\n2. mid\n3. hot");
        int tempInput = scanner.nextInt();

        System.out.println("Select Portion Size:\n1. small\n2. medium\n3. large");
        int portionInput = scanner.nextInt();

        System.out.print("Budget in ₹: ");
        int budget = scanner.nextInt();

        String question = String.format(
                "Which dish matches Mood %d, Taste %d, Texture %d, Temperature %d, Portion %d under ₹%d?",
                moodInput, tasteInput, textureInput, tempInput, portionInput, budget
        );

        cravingMemory.add(question);
        System.out.println("\n🌀 Lashtára Asks: " + question);

        // 🧮 Cravins Calculation
        for (Food f : pool) {
            int mismatch = 0;
            mismatch += Math.abs(moodInput - moodMap.get(f.mood));
            mismatch += Math.abs(tasteInput - tasteMap.get(f.taste));
            mismatch += Math.abs(textureInput - textureMap.get(f.texture));
            mismatch += Math.abs(tempInput - tempMap.get(f.temp));
            mismatch += Math.abs(portionInput - portionMap.get(f.portion));
            mismatch += f.price > budget ? 2 : 0;

            f.cravins = 25 - mismatch; // Scale of resonance
        }

        pool.sort((a, b) -> b.cravins - a.cravins);

        boolean hasSuggestion = false;
        System.out.println("\n🌸 Cravins Recommendations:");
        for (Food f : pool) {
            if (f.cravins >= 18) {
                hasSuggestion = true;
                System.out.printf("» %s 💫 Cravins: %d\n   (%s, %s-textured, %s temp, ₹%d, %s portion)\n\n",
                        f.name, f.cravins, f.taste, f.texture, f.temp, f.price, f.portion);
            }
        }

        if (!hasSuggestion) {
            System.out.println("\n😔 No highly resonant matches. Try adjusting inputs.");
        }

        System.out.println("\n📜 Craving Log:");
        for (String log : cravingMemory) {
            System.out.println("• " + log);
        }

        System.out.println("\n🔮 May Lashtára's Cravins Engine refine hunger with soul.");
    }
}

---

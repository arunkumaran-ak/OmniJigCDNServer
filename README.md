# Omni Jig

A polished, highly modular casual puzzle game developed in Unity for iOS and Android. Omni Jig challenges players across all age groups to solve jigsaw puzzles modeled after the JigSolitaire game. The project is built completely from scratch using robust software engineering practices, dynamic runtime generation, and a fully functional LiveOps asset pipeline.

## Core Gameplay

* **Objective:** Solve interlocking jigsaw puzzle images.


* **Collections:** The game features multiple categories, such as food, animals, and pets.


* **Content Volume:** The initial release includes 9 collections, with 9 puzzles per collection, totaling 81 unique puzzles.


* **Safe Licensing:** All puzzle images strictly utilize public domain or royalty-free assets to avoid IP infringement.



## Technical Architecture

* **Design Principles:** The codebase strictly adheres to SOLID principles and utilizes structural design patterns.


* **Game Flow:** A State Machine handles the overarching game flow and transitions.


* **Runtime Generation:** The Factory Pattern is used to dynamically instantiate all UI elements and puzzle pieces at runtime via C# scripts.


* **LiveOps & CDN:** Every image (excluding core UI) is marked as an Addressable asset.


* **Remote Content:** Puzzle assets and JSON configurations are fetched asynchronously from a dedicated GitHub Pages CDN.


* **Dynamic Data:** `LevelLibraryData` ScriptableObjects are overwritten at runtime using external JSON files downloaded from the CDN, allowing for instant level updates without requiring a new app store build.



## Scene Flow

The game utilizes a lightweight, five-scene structure:

* **`0_SplashScene`:** Boots the application and initializes core managers like Audio, Data, and Addressables.


* **`1_HomeScene`:** Acts as the main menu, displays the first collection's 9 images, and contains a Settings popup.


* **`2_CollectionScene`:** Displays a grid containing all 9 available puzzle collections.


* **`3_GameScene`:** The core puzzle-solving environment featuring runtime puzzle generation and its own Settings popup.


* **`4_LevelClearScene`:** The victory screen displayed after a player successfully clears a level.



## Development Environment

* **Engine:** Unity.


* **Editor:** Cursor IDE, natively linked to Unity for AI-assisted C# development.


* **Version Control:** Managed via Git, utilizing macOS and Unity specific `.gitignore` rules to keep the codebase lightweight and clean.

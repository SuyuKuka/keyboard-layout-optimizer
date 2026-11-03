# Text Analyzer and Keyboard Layout Evaluator

## About

**Text Analyzer and Keyboard Layout Evaluator** is a Java-based software suite developed a third-year Bachelor's (L3) project at Université Paris Cité. Built entirely from scratch in Java 21, the project follows clean object-oriented design principles (immutability, records, enums, programming to interfaces) and implements concurrent data processing.

The project consists of two core modules:
1. **Corpus Text Analyzer (Software 1):** Processes text corpora in parallel using multi-threading to extract character frequencies and N-grams (1, 2, and 3-grams), exporting results into structured CSV files.

2. **Keyboard Layout Evaluator (Software 2):** Parses JSON keyboard layouts (such as AZERTY) and evaluates text corpora against ergonomic criteria (such as Same-Finger Bigrams, Scissors, Lateral Stretches, Rolls, and Alternations) to compute a weighted overall score out of 100.

*Note: The source code and comments may contain some French notes.*

## Tech Stack

- **Language:** Java
- **Build System & Dependency Management:** Gradle 8.8 (with Wrapper)
- **External Libraries:** GSON (`JSON parsing`), JSON-Java (`org.json`), JUnit 5 (`testing`)
- **Architecture:** Object-Oriented Design, Multi-threading (Concurrent processing), Model-View separation.

## Key Features

- **Parallel Text Processing:** Analyzes multiple text files concurrently using threads and safely aggregates N-gram occurrences into a shared thread-safe map.
- **Configurable Layouts & JSON Support:** Fully externalized keyboard configurations (`keyboard.json`) mapping keys, rows, columns, and fingers without hardcoded data.
- **Advanced Ergonomic Scoring:** Evaluates typing mechanics (finger effort, hand balance, bad movements vs. fluid rolls/alternations) based on corpus N-gram frequencies.
- **Automated Testing:** Comprehensive unit and integration tests using JUnit 5.

## Project Structure

```text
📁 keyboard-layout-optimizer/
│
├── 📁 app/
│   └── 📁 src/
│       ├── 📁 main/
│       │   ├── 📁 java/
│       │   │   └── 📁 random/
│       │   │       ├── 📁 analyzer/    # Software 1: Corpus Analyzer & Parser
│       │   │       └── 📁 evaluator/   # Software 2: Keyboard Layout Evaluator
│       │   └── 📁 resources/           # Corpus files
│       └── 📁 test/                    # Unit & integration tests
│
├── 📁 demos/                           # Reference code and library usage demos
├── 📁 docs/                            # AUTHOR & UML files 
├── 📁 gradle/                          # Gradle wrapper and build configuration files
├── 📁 resources/                       # Input corpora, JSON layouts, and generated CSVs
├── 📄 gradlew                          # Gradle wrapper shell script for Unix/Linux/macOS
├── 📄 gradlew.bat                      # Gradle wrapper batch script for Windows
├── 📄 LICENSE                          # License of the project
├── 📄 README.md                        # Project documentation
└── 📄 settings.gradle                  # Root Gradle configuration
```

## Getting Started

### Prerequisites

* Java Development Kit (JDK 21 or higher)
* Gradle Wrapper is included (./gradlew), so no manual Gradle installation is required.

### Installation & Execution

1. Clone the repository:
```bash
git clone https://github.com/SuyuKuka/keyboard-layout-optimizer
cd keyboard-layout-optimizer
```

2. Run Software 1 (Corpus Analyzer):
```bash
./gradlew :app:run1
```

*This analyzes the input corpus files (e.g., in `app/src/main/ressources/`) and generates ngrams.csv.*

3. Run Software 2 (Keyboard Layout Evaluator):
```bash
./gradlew :app:run2
```

*This evaluates the keyboard layout using the generated N-grams and outputs the ergonomic score.*

4. Run Tests:
```bash
./gradlew :app:test
```

## Team

This project was developed collaboratively as a 2-person team:

- **CHEN Michel** - Java Development & Core Logic
  [![GitHub](https://img.shields.io/badge/GitHub-Profile-181717?logo=github)](https://github.com/SuyuKuka)
  [![LinkedIn](https://img.shields.io/badge/LinkedIn-Profile-0A66C2?logo=linkedin)](https://linkedin.com/in/chen-michel)

- **ROIG Lucas** - Java Development & Core Logic
  [![GitHub](https://img.shields.io/badge/GitHub-Profile-181717?logo=github)](https://github.com/ll-tykas)

## License

This project is licensed under the GPL 3.0 License — see [LICENSE](LICENSE) for details.
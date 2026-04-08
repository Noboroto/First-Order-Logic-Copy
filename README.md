# First-Order Logic - SWI-Prolog Simulator

An Artificial Intelligence project that implements a **Forward Chaining inference engine** in C# to simulate SWI-Prolog's first-order logic reasoning. The system parses Prolog-style knowledge bases (facts and rules) and answers queries using forward chaining.

## Team Members

- Nguyen Quoc Huy
- Vo Thanh Tu
- Le Hoang Sang
- Vo Pham Thanh Phuong

## Project Structure

```
├── SWI_Simulation/        # Core inference engine (C# / .NET 7.0)
│   ├── Program.cs          # Entry point - reads KB files and runs queries
│   ├── LogicProcess.cs     # Forward chaining algorithm
│   └── DataType/           # Data structures (KnowledgeBase, Rule, Query, Tern)
├── FiveExample/            # 5 Prolog example files (Ex01.pl - Ex05.pl)
├── AnimalWeb/              # Animal taxonomy knowledge base with diagrams
├── RoyalFamily/            # British Royal Family knowledge base
└── Self-collected knowledge base.xlsx
```

## How It Works

1. **Parse** a Prolog-style `.pl` file containing facts, rules, and queries
2. **Build** a knowledge base of facts and inference rules
3. **Forward Chain** — iteratively apply rules to derive new facts until the query is satisfied or no new facts can be inferred
4. **Answer** queries with variable bindings (e.g., `X = Tiger`)

## Knowledge Bases

### Animal Taxonomy (`KB.pl`)
Classifies animals into Kingdom > Class > Order > Family > Species hierarchy. Supports queries like species membership, same-family checks, competition/predation relationships, and flight capability.

### Royal Family (`RoyalFamily.pl`)
Models the British Royal Family with relationships: parent, married, divorced. Derives: father, mother, sibling, uncle, aunt, grandparent, and more.

## Getting Started

### Prerequisites
- [.NET 7.0 SDK](https://dotnet.microsoft.com/download/dotnet/7.0)

### Run
```bash
cd SWI_Simulation
dotnet run
```

When prompted, provide the path to a knowledge base file (e.g., `KB.pl` or `royal_family.pl`) and an output file path for results.

## Example

```prolog
% Fact
parent(john, mary).

% Rule
father(Parent, Child) :- male(Parent), parent(Parent, Child).

% Query
?- father(john, mary).
```
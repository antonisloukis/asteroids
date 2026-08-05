# Contributing to Asteroids

Thank you for your interest in contributing to **Asteroids**!

Asteroids is a Python game project created for programming practice and learning. Contributions that improve the code, documentation, gameplay, performance, or overall project structure are welcome.

Please read these guidelines before opening an issue or submitting a pull request.

---

## Ways to Contribute

You can contribute by:

- Reporting bugs
- Fixing existing bugs
- Improving documentation
- Refactoring or simplifying code
- Improving game performance
- Suggesting gameplay improvements
- Adding sound effects or visual effects
- Improving collision detection
- Adding tests
- Adding small, focused features
- Improving installation and setup instructions

---

## Before You Begin

Before working on a contribution:

1. Check the existing issues and pull requests.
2. Make sure someone is not already working on the same change.
3. Open an issue before starting a large feature or major redesign.
4. Keep each contribution focused on one specific improvement.

Small bug fixes and documentation improvements usually do not require an issue first.

---

## Development Requirements

To work on this project, you should have:

- Git
- Python
- `uv`
- A GitHub account

You can verify the tools are installed with:

```bash
git --version
python --version
uv --version
```

---

## Setting Up the Project

### 1. Fork the repository

Open the repository on GitHub and select **Fork**.

This creates a copy of the repository under your GitHub account.

### 2. Clone your fork

Replace `YOUR-USERNAME` with your GitHub username:

```bash
git clone https://github.com/YOUR-USERNAME/asteroids.git
cd asteroids
```

### 3. Add the original repository as an upstream remote

```bash
git remote add upstream https://github.com/antonisloukis/asteroids.git
```

Confirm that the remotes were added correctly:

```bash
git remote -v
```

You should see:

- `origin` pointing to your fork
- `upstream` pointing to the original repository

### 4. Install the project dependencies

```bash
uv sync
```

### 5. Run the game

```bash
uv run python main.py
```

Make sure the game starts correctly before making changes.

---

## Creating a Branch

Do not make contributions directly on the `main` branch.

First, make sure your local `main` branch is current:

```bash
git checkout main
git fetch upstream
git merge upstream/main
```

Create a new branch for your change:

```bash
git checkout -b feature/your-feature-name
```

Examples:

```bash
git checkout -b feature/add-score-system
git checkout -b fix/collision-detection
git checkout -b docs/improve-installation-guide
```

Recommended branch prefixes:

- `feature/` for new features
- `fix/` for bug fixes
- `docs/` for documentation changes
- `refactor/` for code restructuring
- `test/` for test-related changes
- `chore/` for maintenance work

---

## Making Changes

When modifying the project:

- Keep your changes focused and reasonably small.
- Follow the existing project structure.
- Follow the existing Python coding style.
- Use descriptive names for variables, functions, classes, and files.
- Avoid unrelated changes in the same pull request.
- Remove debugging code before submitting.
- Do not commit generated files or local environment files.
- Add comments only when they explain something that is not obvious from the code.
- Update the documentation when behavior or setup instructions change.

Avoid committing:

- Virtual environments
- IDE configuration files
- Temporary files
- Cache directories
- Personal settings
- Secrets, passwords, or API keys

---

## Python Style Guidelines

Follow standard Python conventions:

- Use four spaces for indentation.
- Use `snake_case` for variables and functions.
- Use `PascalCase` for classes.
- Use uppercase names for constants.
- Keep functions focused on one responsibility.
- Prefer clear code over unnecessarily clever code.
- Add type hints where they improve clarity.
- Keep imports organized.
- Remove unused imports and unreachable code.

Example:

```python
class Asteroid:
    def update_position(self, delta_time: float) -> None:
        self.position += self.velocity * delta_time
```

---

## Testing Your Changes

Before submitting a pull request, run the game:

```bash
uv run python main.py
```

Check that:

- The game starts without errors.
- Player movement still works.
- Shooting still works.
- Asteroids appear and move correctly.
- Collision detection still works.
- The game closes correctly.
- Your new feature works as expected.
- Your change has not broken existing behavior.

For gameplay or visual changes, test the feature several times under different conditions.

If tests are added to the project, run the complete test suite before submitting your pull request.

---

## Commit Guidelines

Use clear and descriptive commit messages.

Good examples:

```text
Add player score tracking
Fix asteroid collision detection
Improve game setup instructions
Refactor player movement logic
Add sound effect configuration
```

Avoid vague messages such as:

```text
Update
Changes
Fix stuff
Work
Final version
```

Try to keep each commit focused on one logical change.

Stage and commit your changes:

```bash
git add .
git commit -m "Add player score tracking"
```

---

## Keeping Your Branch Updated

Before submitting your pull request, update your branch with the latest version of the original repository:

```bash
git fetch upstream
git checkout main
git merge upstream/main
git checkout feature/your-feature-name
git merge main
```

Resolve any merge conflicts and test the game again.

---

## Pushing Your Changes

Push your branch to your GitHub fork:

```bash
git push origin feature/your-feature-name
```

GitHub will then allow you to open a pull request.

---

## Submitting a Pull Request

When opening a pull request:

1. Target the original repository's `main` branch.
2. Use a clear and descriptive title.
3. Explain what you changed.
4. Explain why the change is useful.
5. Describe how you tested it.
6. Link any related issue.
7. Include screenshots or recordings for visual or gameplay changes.
8. Keep the pull request focused on one feature or fix.

Example pull-request title:

```text
Add player score tracking
```

Example pull-request description:

```markdown
## Summary

Adds a score counter that increases whenever the player destroys an asteroid.

## Changes

- Added a player score variable
- Increased the score after successful asteroid collisions
- Displayed the score during gameplay

## Testing

- Started the game successfully
- Destroyed multiple asteroids
- Confirmed that the score updates correctly
- Confirmed that existing movement and shooting still work

## Related Issue

Closes #12
```

---

## Reporting Bugs

Before reporting a bug:

1. Check that the bug has not already been reported.
2. Make sure you are using the latest project version.
3. Reproduce the problem more than once when possible.

A useful bug report should include:

- A clear title
- A description of the problem
- Steps to reproduce it
- The expected behavior
- The actual behavior
- Relevant error messages
- Your operating system
- Your Python version
- Screenshots or recordings when useful

Example:

```markdown
## Bug Description

The game crashes when the player collides with two asteroids at the same time.

## Steps to Reproduce

1. Start the game.
2. Move toward a group of asteroids.
3. Collide with two asteroids simultaneously.
4. Observe the crash.

## Expected Behavior

The game should detect the collision and end normally.

## Actual Behavior

The game closes and displays an error.

## Environment

- Operating system: Windows 11
- Python version: 3.x
- Installation method: uv
```

---

## Suggesting Features

Feature suggestions are welcome.

A useful feature request should explain:

- The problem or limitation
- The proposed feature
- Why it would improve the project
- Possible implementation ideas
- Any alternatives you considered

Please open an issue before implementing a large feature so it can be discussed first.

---

## Contributions That May Not Be Accepted

A contribution may be declined when it:

- Breaks existing functionality
- Introduces unnecessary complexity
- Contains unrelated changes
- Does not follow the project structure
- Duplicates an existing contribution
- Adds a major feature without prior discussion
- Includes copyrighted material without permission
- Includes secrets, credentials, or sensitive information
- Does not follow the Code of Conduct

A declined contribution is not necessarily a bad contribution. It may simply not fit the project's current direction.

---

## Review Process

After submitting a pull request:

- The code may be reviewed and tested.
- Changes may be requested.
- You may need to update your branch.
- Discussions should remain respectful and focused on the contribution.
- The pull request may be merged, closed, or postponed depending on the project's needs.

Please do not open duplicate pull requests for the same change.

---

## Code of Conduct

All contributors must follow the repository's [Code of Conduct](CODE_OF_CONDUCT.md).

Be respectful, constructive, and professional when communicating through issues, discussions, reviews, and pull requests.

---

## License

By contributing to this repository, you agree that your contributions may be distributed under the same license as the project.

---

Thank you for helping improve Asteroids!

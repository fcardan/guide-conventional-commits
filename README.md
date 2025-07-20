# 📖 Guide: Conventional Commits

## 🔹 Introduction
The repository provides a structured approach to implementing and adhering to the Conventional Commits specification in software development projects. This pattern emphasizes clear, consistent, and meaningful commit messages, which improve collaboration, versioning, and changelog generation.

---
⠀
## 🔹 Why This Format?
Adopting a standardized format for commit messages:

✅ Enables automated changelog generation

✅ Simplifies change tracking and auditing

✅ Improves collaboration in team environments

✅ Integrates with modern DevOps toolchains

✅ Aligns with industry best practices

---
⠀
⠀
⠀
## 🔹 Best Practice Checklist

✅ Use imperative mood ("Add feature" not "Added feature")

✅ Keep descriptions ≤50 characters

✅ Reference issues/PRs in footers

✅ Separate distinct changes into atomic commits

✅ Document breaking changes explicitly

✅ Maintain consistent terminology

> "Treat commit messages like you're explaining your changes to a future developer who will maintain your code." – _Industry Best Practice_

---
⠀
⠀
⠀
## 🔹 Commit Structure
```text
<type>(<scope>): <short description>

[optional body]

[optional footer]
```
⠀
⠀
⠀
## 🔹 Key Component


| Element          | Required | Description                                                                 |
|------------------|----------|-----------------------------------------------------------------------------|
| **Type**         | ✔️       | Change category (see valid types below)                                     |
| **Scope**        | ❌       | Affected component (e.g., `dashboard`, `payment-gateway`, `api/v2`)        |
| **Description**  | ✔️       | Concise imperative statement ("Update" not "Updated" or "Updating")        |
| **Body**         | ❌       | Context or implementation details                                          |
| **Footer**       | ❌       | References to issues, breaking changes, or co-authors                       |

⠀
⠀
⠀
## 🔹 Valid Change Types


| **Type**   | **Use Case**                          |
|------------|---------------------------------------|
| feat       | New user-facing functionality        |
| fix        | Bug resolution                        |
| docs       | Documentation improvements            |
| style      | Code formatting (whitespace, syntax)  |
| refactor   | Code restructuring without behavior change |
| test       | Test suite modifications              |
| chore      | Dependency updates/maintenance tasks  |
| build      | Build system configuration            |
| ci         | CI/CD pipeline changes                |
| perf       | Performance optimizations             |
| revert     | Revert previous changes               |
| security   | Security-related patches              |

⠀
⠀
⠀

⠀
⠀
⠀
## 🔹 Practical Examples

#### Feature implementation:
```git
feat(authentication): add multi-factor auth option
```
#### Bug fix with breaking change:
```git
fix(database)!: update schema validation
BREAKING CHANGE: Requires MySQL 8.0+
```
#### Documentation update:
```git
docs(api): clarify rate limiting policies
```
#### Performance optimization:
```git
perf(rendering): reduce bundle size by 20%
Issue: #456
```

## 🔹 AI Commit Message Generator Prompt

Use this prompt with DeepSeek's **"Search"** to generate standardized commit messages based on your code changes.

### How to Use

1. **Prepare Your Updates**  
   Replace the bullet points under `UPDATE` with your actual changes (be specific).

2. **Run in DeepSeek**  
   - Open DeepSeek Chat
   - Enable **"Search"** (web access)
   - Paste this prompt:

```text
INSTRUCTIONS:
1. Change Analysis  
   - Identify dominant theme (e.g., docs/feat/fix)  
   - Group related changes under same scope  

2. Type Selection  
   - Priority: `fix` > `feat` > `docs` > `chore`  
   - Use `refactor` only for non-functional code reorganization  

3. Formatting Rules  
   - English descriptions only  
   - Omit articles (a/an/the) and final punctuation  
   
4. Version Assessment (Apply SemVer rules):
   - BREAKING CHANGE → Major (X+1.0.0)
   - feat → Minor (0.X+1.0)
   - fix → Patch (0.0.X+1)

REASONING STEPS
1. List all changes from UPDATES  
2. Categorize by type/impact  
3. Determine if scope adds essential context  
4. Draft 3 message options  
5. Validate against:  
   - [x] Brevity (<50 chars)  
   - [x] Conventional Commits compliance  

OUTPUT FORMAT 
<type>(<scope>): <concise_description>  
NEW_VERSION: <new_version> (if applicable)  

Golden Rule:
"If you remove (scope), does the message still make sense?"

EXAMPLES

Example 1 (docs + scope):

CURRENT_VERSION: 1.4.2  
Updates:
- Update compatibility table in README
- Fix broken installation links

Output:
docs(readme): update compatibility table & fix links  

Example 2 (fix without scope):

CURRENT_VERSION: 1.4.2  
Updates:
- Resolve NaN error in calculate_yield
- Add timezone validation

Output:
fix: handle NaN values in yield calculation  
NEW_VERSION: 1.5.0 

FINAL STRUCTIONS:

Think step-by-step:

- What's the primary impact of changes?
- Which type best communicates this to maintainers?
- How to simplify without losing essential context?

CONTEXT:
Target repo: {your repo here}
Reference standard: https://github.com/fcardan/guide-conventional-commits

EXECUTE WITH: 

CURRENT_VERSION: {semver}
CONTEXT: {Describe task context}  
UPDATES:  
- {Change 1}  
- {Change 2}  
- {Change 3}  

Generate Conventional Commits message:
```

### Expected Output

After running the prompt, you’ll receive a commit suggestion like this:

```text
fix(xpath): correct node selection logic in PHP script
```


## 🔹 References

- https://www.conventionalcommits.org/
- https://seesparkbox.com/foundry/semantic_commit_messages
- http://karma-runner.github.io/1.0/dev/git-commit-msg.html 


## 🔹 License

This repository is licensed. This means you are free to share and adapt this content for any purpose, even commercially, as long as you provide appropriate credit to the original author. For more details, please refer to the [LICENSE.md](https://github.com/fcardan/conventional-commits-pattern/blob/main/LICENSE.md) file.

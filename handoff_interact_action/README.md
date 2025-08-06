# Handoff Interact Action

![GitHub release (latest by date)](https://img.shields.io/github/v/release/TrueSelph/handoff_interact_action)
![GitHub Workflow Status](https://img.shields.io/github/actions/workflow/status/TrueSelph/handoff_interact_action/test-handoff_interact_action.yaml)
![GitHub issues](https://img.shields.io/github/issues/TrueSelph/handoff_interact_action)
![GitHub pull requests](https://img.shields.io/github/issues-pr/TrueSelph/handoff_interact_action)
![GitHub](https://img.shields.io/github/license/TrueSelph/handoff_interact_action)

This action is designed to seamlessly handle queries or tasks that the agent cannot resolve independently. It silently transfers unresolved queries to a human operator. Once the required information or resolution is obtained, the action updates the relevant store with the response and notifies the user. Configured as a singleton, it ensures that only one instance is operational at any given time.

## Package Information

- **Name:** `jivas/handoff_interact_action`
- **Author:** [V75 Inc.](https://v75inc.com/)
- **Architype:** `HandoffInteractAction`
- **Version:** 0.1.0

## Meta Information

- **Title:** Handoff Interact Action
- **Description:** This action is designed to seamlessly handle queries or tasks that the agent cannot resolve independently. It silently transfers unresolved queries to a human operator. Once the required information or resolution is obtained, the action updates the relevant store with the response and notifies the user.
- **Group:** custom
- **Type:** interact_action

## Configuration

- **Singleton:** true
- **Order:**
  - **Weight:** 5
  - **After:** persona_interact_action

## Dependencies

- **Jivas:** 2.1.0
- **Actions:**
  - `jivas/persona_interact_action`: ^0.1.0
  - `jivas/typesense_vector_store_action`: ^0.1.0

---

### Handoff Action Process

#### Step 1: Create and Share Worksheet

- **Fields**:
  - `id`
  - `session_id`
  - `query`
  - `answer`
  - `status`
  - `expert`

Utilize the Google Sheets API to create a worksheet with the above fields and share it with the designated Google Sheets API email for collaboration.

#### Step 2: Manage Data Storage

- **google_sheet_enabled**: Opt to utilize the store instead of Google Sheets for data management.
- **update_store**: Enable to update the agent knowledge.

The Handoff Interact Action optimizes workflow by interfacing between automated processes and human intervention, ensuring efficiency and accuracy in handling unresolved queries.

---

## 🚀 Setup Guide

### Step 1: Install Dependencies

Ensure that the required dependencies are installed:
- `jivas/persona_interact_action`
- `jivas/typesense_vector_store_action`

### Step 2: Configure the Action

Update the configuration file to include the necessary credentials and dependencies.

---

## 🔰 Contributing

- **🐛 [Report Issues](https://github.com/TrueSelph/handoff_interact_action/issues)**: Found a bug or want to request a feature? Submit it here.
- **💡 [Submit Pull Requests](https://github.com/TrueSelph/handoff_interact_action/blob/main/CONTRIBUTING.md)**: Check out open PRs or submit your own improvements.

<details closed>
<summary>Contributing Guidelines</summary>

1. **Fork the Repository**: Start by forking the project repository to your GitHub account.
2. **Clone Locally**: Clone the forked repository to your local machine using a git client.
   ```sh
   git clone https://github.com/TrueSelph/handoff_interact_action
   ```
3. **Create a New Branch**: Always work on a new branch, giving it a descriptive name.
   ```sh
   git checkout -b new-feature-x
   ```
4. **Make Your Changes**: Develop and test your changes locally.
5. **Commit Your Changes**: Commit with a clear message describing your updates.
   ```sh
   git commit -m 'Implemented new feature x.'
   ```
6. **Push to GitHub**: Push the changes to your forked repository.
   ```sh
   git push origin new-feature-x
   ```
7. **Submit a Pull Request**: Create a PR against the original project repository. Clearly describe the changes and their motivations.
8. **Review**: Once your PR is reviewed and approved, it will be merged into the main branch. Congratulations on your contribution!
</details>

<details open>
<summary>Contributor Graph</summary>
<br>
<p align="left">
    <a href="https://github.com/TrueSelph/handoff_interact_action/graphs/contributors">
        <img src="https://contrib.rocks/image?repo=TrueSelph/handoff_interact_action" />
   </a>
</p>
</details>

## 🎗 License

This project is protected under the Apache License 2.0. See [LICENSE](../LICENSE) for more information.
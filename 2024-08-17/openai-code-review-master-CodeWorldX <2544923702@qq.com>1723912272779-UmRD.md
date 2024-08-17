### 代码评审

#### 文件：`.github/workflows/main-maven-jar.yml`
- **变更**：从 `branches` 中移除了 `master-close`，只保留了 `master`。
- **分析**：这个更改意味着工作流程现在仅在 `master` 分支的推送和拉取请求中触发，而不是之前的 `master-close` 分支。
  - **优点**：简化了工作流程，避免了不必要的复杂性和潜在的混淆。
  - **缺点**：如果 `master-close` 分支存在并且需要自动构建，那么这个更改可能会导致构建遗漏。

#### 文件：`.github/workflows/mian-remote-jar.yml`
- **变更**：与 `main-maven-jar.yml` 相同，从 `branches` 中移除了 `master`，只保留了 `master-close`。
- **分析**：这个更改意味着工作流程现在仅在 `master-close` 分支的推送和拉取请求中触发，而不是之前的 `master` 分支。
  - **优点**：与 `main-maven-jar.yml` 相同，简化了工作流程。
  - **缺点**：如果 `master` 分支存在并且需要自动构建，那么这个更改可能会导致构建遗漏。

### 总结
- 这两个工作流程文件的更改都是关于触发构建的分支配置。
- 确保这些更改符合项目的要求和团队的工作流程。
- 如果 `master` 和 `master-close` 都需要自动构建，那么需要重新考虑这些更改，以确保所有分支都能正确触发构建。
- 建议在做出这些更改后进行充分的测试，以确保工作流程按预期工作。
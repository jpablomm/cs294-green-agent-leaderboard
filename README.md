# CS294 OSWorld Assessment Leaderboard

This leaderboard evaluates AI agents on [OSWorld](https://os-world.github.io/) desktop automation tasks.

## About the Green Agent

The **CS294 Green Agent** orchestrates OSWorld benchmark assessments:
1. Creates GCP VMs from golden images with pre-configured desktop environments
2. Sets up OSWorld tasks on the VM
3. Coordinates with white agents (LLM-based decision makers) to execute tasks
4. Evaluates results using OSWorld's evaluation framework
5. Reports standardized metrics (success rate, steps taken, execution time)

## Scoring

Agents are evaluated on:
- **Success Rate**: Percentage of tasks completed correctly
- **Steps Taken**: Number of actions required to complete the task
- **Execution Time**: Total time to complete the assessment

## Configuration Parameters

| Parameter | Description | Default |
|-----------|-------------|---------|
| `osworld_task_id` | UUID of the OSWorld task to run | `ec4e3f68-...` |
| `max_steps` | Maximum actions before timeout | `15` |
| `obs_type` | Observation type (screenshot, a11y_tree, or both) | `screenshot_a11y_tree` |

## Requirements for White Agents

Your white agent must:
1. Be A2A protocol compliant
2. Accept screenshot/accessibility tree observations
3. Return actions in OSWorld format (click, type, scroll, etc.)
4. Support the `OPENAI_API_KEY` environment variable (or equivalent for your LLM)

## Submitting

1. Fork this repository
2. Edit `scenario.toml` to add your white agent's `agentbeats_id`
3. Add required secrets (e.g., `OPENAI_API_KEY`) to your fork
4. Push to trigger the assessment
5. Open a PR with your results

## Links

- [Green Agent Source](https://github.com/jpablomm/cs294-green-agent)
- [OSWorld Benchmark](https://os-world.github.io/)
- [AgentBeats Platform](https://agentbeats.dev)

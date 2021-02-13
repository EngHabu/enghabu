# Flyte Meetup Notes

[YouTube Channel](https://www.youtube.com/channel/UCNduEoLOToNo3nFVly-vUTQ/)

[Video Archives](https://drive.google.com/drive/folders/1Op9EzMNuoZptWovcZcYVdmAuJNNNjil4?usp=sharing)

## Backlog Agenda Items
* * Lyft deployment of Flyte architecture/design [Anmol - Lyft]
* Flyte-Flink [Philip - Spotify]
* Freenome deployment of flyte architecture/design [Jeev - Freenome]
* Katacoda Tutorial [Yuraj - OSC]
* Kickoff Reactive pipelines design [Haytham - OSC]
* Client-side caching [Katrina - OSC]
* SDK-Roadmap [Yee - OSC]
* Documentation overview [Katrina - OSC]
* Getting Started - FAST
* L5 deployment of Flyte architecture/design [Miguel - L5 Lyft]
* Lyft-Minsk deployment of Flyte architecture/design [Ruslan- Minsk Lyft]

## Feb 9, 2021

### [YouTube Video](https://www.youtube.com/watch?v=iHBUxzSC9XE)

### Agenda:
* Flyte Egress Events [Sonja - Katrina - Nian - Spotify]
* Flyte at Lyft L5 Autonomous cars using Bazel [Miguel - Lyft L5]
* Planning [Ketan - OSC]

### Notes: by @katrogan
Egress Events (Presenter: Nian Tang from Spotify)
* Spotify is working on lineage integration with Flyte workflows, want to enrich events before sending to their internal system
* Proposed event flow: first process and enrich events in FlyteAdmin and then forward to a streaming pubsub which can subsequently be read by downstream consumers
* Ongoing work: enriched event flyteidl PR, publish raw events in FlyteAdmin
* Suggestion: integrate this work with datacatalog and other open source systems to produce enriched data natively

Flyte at Level 5 (Presenter: Miguel Toledo Zavala from Lyft Level 5)
* Run Flyte on EKS managed k8s deployment, largely mono repo with Bazel as a build system
* L5 has defined a customized Bazel rule which uses a py_binary for a workflow
* Use a command line tool to invoke the build rule and publish workflows, and to trigger executions
* Reduced iteration time from hours to minutes(!)
* Pending open source release after integration with new flytekit

Planning (Presenter: Ketan Umare from new company)
* Ironing out the user experience with flytekit, user docs in flytesnacks
* Improved onboarding experience: just a few lines to get started on flyte and deploying examples
* [Roadmap](https://flyte.readthedocs.io/en/latest/introduction/roadmap.html#upcoming-features-issues)
* Haytham presented the new [webapi back-end plugin](https://github.com/flyteorg/flyteplugins/blob/master/go/tasks/pluginmachinery/webapi/plugin.go) for integration with external web services
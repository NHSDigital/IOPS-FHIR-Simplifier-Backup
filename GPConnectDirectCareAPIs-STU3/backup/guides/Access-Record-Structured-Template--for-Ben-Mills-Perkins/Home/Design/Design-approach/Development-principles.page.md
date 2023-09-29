## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
<b>Summary</b>: High-level principles related to the development of the system
</div>

1. Software assets to be held on [GitHub](https://github.com/nhsconnect).

2. Software to be licensed under the [Apache 2 license](https://www.apache.org/licenses/LICENSE-2.0).

3. Code repositories will use the [GitFlow](https://nvie.com/posts/a-successful-git-branching-model/) branching model.

    - Contributors make changes by submitting [pull requests](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests).

    - Editors review pull requests for consistency prior to merging into `develop`.

    - Periodically, editors create a `release` candidate (where appropriate, editors will seek wider review of release candidate assets including clinical review, Connectathon testing and so on).

    - Following successful review, assets are marked as active and published to `master` branch.

4. Software assets will follow [Semantic Versioning](https://semver.org/).
    - Major versions will be maintained in parallel for a period of time before deprecation.

5. GitHub [webhooks](https://docs.github.com/en/developers/webhooks-and-events/webhooks/about-webhooks) will be used to automatically build and publish software assets to a public test instance.

---

</br>
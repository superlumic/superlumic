# Superlumic

Superlumic is an light utility wrapper around Ansible to ease the automated install of OSX 10.10 and higher. It uses several roles distilled over years of use in the Chef based predecessor, Kitchenplan.

Since moving to Ansible for my server deploys, I wanted to bring the same experience I created with Kitchenplan to OSX via Ansible. Existing solutions like Battleschool didn't offer the same user experience so I started fresh.

While the Kitchenplan wrapper uses a Ruby gem and quite some code, I will try to keep Superlumic pure Bash and use as much of the Ansible ecosystem and built in features as possible. This will help in extensability and maintenance.

## Installation

```
curl https://raw.githubusercontent.com/superlumic/superlumic/master/superlumic | bash -s setup
```

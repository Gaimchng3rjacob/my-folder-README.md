# eden-key## License

EdenKey is released under the MIT License.  
You are free to use, modify, and distribute this software, provided you retain the original copyright.

See [LICENSE](./LICENSE) for full terms.
import os
from datetime import datetime

class EdenFile:
    def __init__(self, path):
        self.path = path
        self.name = os.path.basename(path)
        self.timestamp = datetime.now()
        self.status = "untracked"

    def track(self):
        self.status = "tracked"
        print(f"📁 Tracking file: {self.name}")

    def __str__(self):
        return f"[{self.status.upper()}] {self.name} | Added: {self.timestamp.strftime('%Y-%m-%d %H:%M')}"
from datetime import datetime

class EdenTask:
    def __init__(self, title, status="open", ritual=None):
        self.title = title
        self.status = status
        self.created = datetime.now()
        self.ritual = ritual or "Unbound"

    def mark_complete(self):
        self.status = "closed"
        print(f"✅ Task '{self.title}' marked complete.")

    def __str__(self):
        return f"[{self.status.upper()}] {self.title} | Ritual: {self.ritual} | Created: {self.created.strftime('%Y-%m-%d %H:%M')}"

# Example usage
tasks = []
tasks.append(EdenTask("Initialize EdenShell CLI", ritual="First Flame"))
tasks.append(EdenTask("Bind Vault to Node Sanctum"))
tasks.append(EdenTask("Deploy Android build via Fastlane"))

for task in tasks:
    print(task)
#!/bin/bash
echo "🌱 Launching EdenKey Sanctum Node..."
edenkey start --node sanctum-alpha --vault ./vault.json --oath "Guard the vulnerable, honor the truth" --ghost --sync --sonic

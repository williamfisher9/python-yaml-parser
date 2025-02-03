# Python YAML File Parser
Python uses PyYaml library to read and write yaml file.

First of all, install PyYaml dependency.
```yaml.sh
pip install pyyaml
```

To read a file with single document:
```yaml.py
import yaml
import pprint

if __name__ == '__main__':
    with open('configs.yaml', 'r') as file:
        prime_service = yaml.safe_load(file)
        pprint.pprint(prime_service, sort_dicts=True, indent=True, width=50, depth=2)
        print(prime_service['prime_numbers'][0])
        print(prime_service['rest']['url'])
```

To read a file with multiple documents:
```yaml.py
import yaml

with open('configs_multi.yaml', 'r') as file:
    docs = yaml.safe_load_all(file)

    for doc in docs:
        print(doc)
```

To write to yaml file:
```yaml.py
import yaml

with open('names.yaml', 'w') as file:
    yaml.dump(prime_service, file)
```

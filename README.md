# yarn-bug-demo

To reproduce:
```
git clone https://github.com/ipanasenko/yarn-bug-demo
cd yarn-bug-demo
git cherry-pick origin/react-17
# fix conflicts ONLY in package.json, accept react ^18.0.0
yarn --mode=update-lockfile
git diff
```

You will see following diff:

<img width="364" alt="image" src="https://github.com/ipanasenko/yarn-bug-demo/assets/576152/40930edc-73e1-4213-a3b4-a547b4a26ef9">

Running simple `yarn` instead of `yarn --mode=update-lockfile` doesn't produce `checksum: undefined` field

Remember to 🌟 this Github if you 💖 it.

> This package contains types definitions for RAGE:MP server-side module.

## 📥 Installation

#### `SERVER-SIDE`

```bash
# With npm
npm i --save-dev github:leonardssh/ragemp-types#types-server

# With yarn
yarn add -D github:leonardssh/ragemp-types#types-server

# With pnpm
pnpm add -D github:leonardssh/ragemp-types#types-server
```

> To make these types detectable, you need to add the `types` property below to `tsconfig.json` on each side of your project.

```json
// e.g server-side
{
	"compilerOptions": {
		"types": ["{RELATIVE_PATH_TO_NODE_MODULES}/@ragemp/types-server"]
	}
}
```

## 🤓 Usage

### Full type-safe and auto-complete

![](https://i.imgur.com/o2JB3Jx.gif)

---

### To extend a Mp object, there are 2 ways:

1. By extend the prototype of the object:

```ts
// which augments the interface of the current PlayerMp object
interface PlayerMp {
	myProperty: number;

	myMethod(): void;
}

mp.Player.prototype.myMethod = function myMethod() {
	// my method logic
};

// Usage
mp.events.add('playerReady', (player) => {
	player.myProperty = 1;

	player.myMethod();
});
```

2. By extend the object itself:

```ts
// which augments the interface of the current PlayerMp object
interface PlayerMp {
	myProperty: number;

	myMethod(): void;
}

mp.events.add('playerReady', (player) => {
	player.myProperty = 1;

	player.myMethod = function myMethod() {
		// my method logic
	};
});
```

See: [Typescript Module Augmentation](https://www.digitalocean.com/community/tutorials/typescript-module-augmentation)

## 👨‍💻 Contributing

To contribute to this repository, feel free to create a new fork of the repository and submit a pull request.

1. Fork / Clone and select the `main` branch.
2. Create a new branch in your fork.
3. Make your changes.
4. Commit your changes, and push them.
5. Submit a Pull Request [here](https://github.com/leonardssh/ragemp-types/pulls)!

## 🎉 Thanks

-   [CocaColaBear](https://github.com/CocaColaBear/) - Creator of [types-ragemp-s](https://github.com/CocaColaBear/types-ragemp-s) & [types-ragemp-c](https://github.com/CocaColaBear/types-ragemp-c)

## 📋 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

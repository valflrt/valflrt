```typescript
interface PersonConfig {
  pseudo: string;

  firstName?: string;
  lastName?: string;
  age?: number;
  pronouns?: string;
  aboutMe?: string;
  nationality?: string;
}

class Person {
  public pseudo: string;

  public firstName?: string;
  public lastName?: string;
  public age?: number;
  public pronouns?: string;
  public aboutMe?: string;
  public nationality?: string;

  constructor(config: PersonConfig) {
    this.pseudo = config.pseudo;

    this.firstName = config.firstName;
    this.lastName = config.lastName;
    this.age = config.age;
    this.pronouns = config.pronouns;
    this.aboutMe = config.aboutMe;
    this.nationality = config.nationality;
  }

  public get description(): string {
    return `• name/pseudo: ${this.fullName}`
      .concat(`\n• age: ${this.age}`)
      .concat(`\n• pronouns: ${this.pronouns}`)
      .concat(this.aboutMe ? `\n• about me: ${this.aboutMe}` : "")
      .concat(this.nationality ? `\n• nationality: ${this.nationality}` : "");
  }

  public get fullName(): string {
    return this.firstName
      ? this.firstName
          .concat(this.lastName ? ` ${this.lastName}` : "")
          .concat(this.pseudo ? ` ${this.pseudo}` : "")
      : this.pseudo;
  }
}

let valflrt = new Person({
  pseudo: "valflrt",
  age: 17,
  pronouns: "he/him",
  aboutMe: "A programming and self deprecation enthusiast",
  nationality: "french",
});

console.log(valflrt.description);
```

```
• name/pseudo: valflrt 
• age: 17 
• pronouns: he/him 
• about me: A programming and self deprecation enthusiast 
• nationality: french
```

<img src="./20220108_144430_edited.jpeg"
     title="help"
     width="256"
/>

# lern-ts-node
lern-ts-node

## install 

````
npm i -g ts-node

pm2 install ts-node 
pm2 install typescript
````

## run

````
ts-node src\main.ts
````

## run transpileOnly

````
ts-node -T src\main.ts

ts-node --transpileOnly src\main.ts

````


# example

````
npm install typescript ts-node
````


## code test

nano test.ts

````
class Reptile {
  private reptiles: Array<string> = [
    'Alligator',
    'Crocodile',
    'Chameleon',
    'Komodo Dragon',
    'Iguana',
    'Salamander',
    'Snake',
    'Lizard',
    'Python',
    'Tortoise',
    'Turtle',
  ];

  shuffle(): void {
    for (let i = this.reptiles.length - 1; i > 0; i--) {
      let j: number = Math.floor(Math.random() * (i + 1));
      let temp: string = this.reptiles[i];
      this.reptiles[i] = this.reptiles[j];
      this.reptiles[j] = temp;
    }
  }

  random(count: number = 1, allowDupes?: boolean): Array<string> {
    let selected: Array<string> = [];

    if (!allowDupes && count > this.reptiles.length) {
      throw new Error(`Can't ensure no dupes for that count`);
    }

    for (let i: number = 0; i < count; i++) {
      if (allowDupes) {
        // Dupes are cool, so let's just pull random reptiles
        selected.push(this.reptiles[
          Math.floor(Math.random() * this.reptiles.length)
        ]);
      } else {
        // Dupes are no go, shuffle the array and grab a few
        this.shuffle();
        selected = this.reptiles.slice(0, count);
      }
    }

    return selected;
  }
}

const reptile = new Reptile();
console.log(`With Dupes: ${reptile.random(10, true)}`);
console.log(`And Without: ${reptile.random(10)}`);
````

## run 

````
C:\Users\admin\Desktop\ts-node-test>ts-node test.ts
With Dupes: Lizard,Turtle,Komodo Dragon,Salamander,Tortoise,Tortoise,Python,Turtle,Snake,Tortoise
And Without: Crocodile,Komodo Dragon,Turtle,Salamander,Snake,Python,Alligator,Tortoise,Iguana,Chameleon

C:\Users\admin\Desktop\ts-node-test>ts-node -T test.ts
With Dupes: Tortoise,Alligator,Lizard,Iguana,Alligator,Tortoise,Lizard,Alligator,Salamander,Salamander
And Without: Tortoise,Crocodile,Python,Salamander,Lizard,Komodo Dragon,Alligator,Chameleon,Iguana,Turtle
````



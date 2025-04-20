import { useState } from "react";
import { Button } from "@/components/ui/button";
import { Card, CardContent } from "@/components/ui/card";

const chapters = [
  {
    title: "Chapter 1: Hello & My Name Is",
    content: `
👋 Hello, kids! I am Sam, your virtual teacher robot. Welcome!

Today we will learn:
- How to say hello
- How to say your name
- How to ask someone's name

📝 Example:
- Hello! My name is Amina. What is your name?
- My name is Adam. Nice to meet you!

📚 Vocabulary:
- Hello /hi/ 👋
- Goodbye /ˈɡʊd.baɪ/ 👋
- Name /neɪm/
- What /wɒt/ | is /ɪz/ | your /jɔːr/

🎧 Try to repeat:
- Hello!
- My name is...
- What is your name?

🧠 Exercise:
Fill in the blanks:
1. Hello! My ____ is Fatima.
2. What is ____ name?
3. Nice to ____ you!

✍️ Dictation:
Listen and write:
- Hello! What is your name?

😂 Joke:
Why did the kid bring a ladder to school?  
Because she wanted to go to high school!

🎥 Video Explanation:  
[Watch here for more on greetings!](https://www.youtube.com/watch?v=dQw4w9WgXcQ)

🖼️ Image Example:  
![Greetings Image](https://via.placeholder.com/600x400.png?text=Greetings+Image)  
    `,
    video: "https://www.youtube.com/watch?v=dQw4w9WgXcQ",
    image: "https://via.placeholder.com/600x400.png?text=Greetings+Image",
  },
  {
    title: "Chapter 2: My Family",
    content: `
👨‍👩‍👧‍👦 Let's talk about family today!

📝 Learn these words:
- Father /ˈfɑːðər/ 👨
- Mother /ˈmʌðər/ 👩
- Brother /ˈbrʌðər/ 👦
- Sister /ˈsɪstər/ 👧
- Family /ˈfæməli/

💬 Example:
- This is my sister.
- Her name is Laila.
- I love my family very much.

🎧 Repeat:
- My father is strong.
- My mother is kind.

🧠 Exercise:
Match:
1. Mother - 👩  
2. Brother - 👦  
3. Sister - 👧

🧩 Fun Question:
Draw your family and write their names in English!

🎥 Video Explanation:  
[Watch here for family words!](https://www.youtube.com/watch?v=dQw4w9WgXcQ)

🖼️ Image Example:  
![Family Image](https://via.placeholder.com/600x400.png?text=Family+Image)  
    `,
    video: "https://www.youtube.com/watch?v=dQw4w9WgXcQ",
    image: "https://via.placeholder.com/600x400.png?text=Family+Image",
  },
  // Continue for other chapters...
];

export default function SamVirtualTeacher() {
  const [currentChapter, setCurrentChapter] = useState(0);

  const nextChapter = () => {
    if (currentChapter < chapters.length - 1) {
      setCurrentChapter(currentChapter + 1);
    }
  };

  const prevChapter = () => {
    if (currentChapter > 0) {
      setCurrentChapter(currentChapter - 1);
    }
  };

  return (
    <div className="min-h-screen bg-sky-200 p-6 font-serif">
      <Card className="max-w-3xl mx-auto shadow-xl rounded-2xl">
        <CardContent className="p-6">
          <h1 className="text-2xl font-bold mb-4 text-black">{chapters[currentChapter].title}</h1>
          <pre className="whitespace-pre-wrap text-base text-gray-800">
            {chapters[currentChapter].content}
          </pre>
          <div className="mt-6">
            {/* Image */}
            <div className="text-center mb-6">
              <img
                src={chapters[currentChapter].image}
                alt="Chapter Illustration"
                className="max-w-full rounded-lg"
              />
            </div>
            {/* Video Link */}
            <div className="text-center mb-6">
              <a href={chapters[currentChapter].video} target="_blank" rel="noopener noreferrer">
                <Button className="bg-green-500 text-white px-4 py-2 rounded-md">Watch Video Explanation</Button>
              </a>
            </div>
          </div>
          <div className="mt-6 flex justify-between">
            <Button onClick={prevChapter} disabled={currentChapter === 0}>
              ⬅️ Previous
            </Button>
            <Button onClick={nextChapter} disabled={currentChapter === chapters.length - 1}>
              Next ➡️
            </Button>
          </div>
        </CardContent>
      </Card>
    </div>
  );
}

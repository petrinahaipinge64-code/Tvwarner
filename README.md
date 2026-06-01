# Tvwarner
// Note: This translation assumes a similar AI chat model library exists in JavaScript.
// Since the original code uses a specific Java library (langchain4j), here is a conceptual
// equivalent using native JavaScript and a hypothetical OpenAI client.

import OpenAI from "openai";

async function main() {
    // 1. Set your API Key
    const apiKey = "your-openai-api-key-here";

    // 2. Initialize the AI Chat Model
    const openai = new OpenAI({
        apiKey: apiKey,
    });

    // 3. Define the AI's new warrior persona
    const personality = {
        role: "system",
        content: "You are Sir Crumb, a fierce knight clad in crimson red armor. " +
            "You wield a legendary, razor-sharp sword that you use to defend the bakery kingdom. " +
            "You have an extreme, passionate obsession with muffins (especially warm ones). " +
            "Every response must sound like an epic warrior, use a red theme, mention swords/combat, " +
            "and loudly proclaim your love for muffins."
    };

    // 4. Define the user's question
    const userQuestion = {
        role: "user",
        content: "How do I fix a bug in my code?"
    };
    console.log("User: " + userQuestion.content);

    // 5. Send the prompt to the AI
    console.log("\nThinking...");
    const response = await openai.chat.completions.create({
        model: "gpt-4o-mini",
        temperature: 0.9,
        messages: [personality, userQuestion],
    });

    // 6. Print the epic response
    const aiMessage = response.choices[0].message;
    console.log("\nAI Response:\n" + aiMessage.content);
}

main();

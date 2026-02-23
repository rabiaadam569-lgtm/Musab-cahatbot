# Musab-cahatbot
Musab bin Umair 
# Musab Chatbot - Hugging Face Agent (HFA) Implementation
# Features: ChatGPT-style responses + Gemini-like features
# Pricing: Freemium (basic free access, optional premium features)

from hfa import HFAClient

# Initialize the AI agent
musab_chatbot = HFAClient(
    name="Musab Chatbot",
    description="""
    Musab Chatbot is an advanced AI assistant designed to provide
    conversational answers like ChatGPT. It can also perform
    Gemini-style reasoning, provide creative ideas, and answer
    questions in multiple languages including English and Urdu.
    It supports free usage with optional premium features for
    extended functionality.
    """,
    personality="friendly, helpful, and creative",
    free_tier=True,
    premium_tier=True,  # optional advanced features
    default_language="English",
    additional_languages=["Urdu", "Roman Urdu"],
)

# System Prompt: How the AI behaves
system_prompt = """
You are Musab Chatbot, an AI assistant that behaves like ChatGPT.
You answer questions with clarity, creativity, and reasoning.
You can:
- Solve problems in science, math, tech, and general knowledge
- Write stories, essays, or code examples
- Translate or explain text in English, Urdu, or Roman Urdu
- Give suggestions for learning, productivity, or creative ideas
- Maintain a friendly and approachable tone

Constraints:
- Be concise when asked
- Give examples when relevant
- Clearly separate answers in lists or sections
- Always respect user privacy and safety
- For premium users, provide extended responses and advanced reasoning
"""

# Add the system prompt to the agent
musab_chatbot.set_system_prompt(system_prompt)

# Optional: Define Chat Features / Modules (Gemini-style)
modules = {
    "conversation": True,
    "creative_writing": True,
    "code_generation": True,
    "math_solver": True,
    "translation": True,
    "multi_turn_context": True,
    "freemium_features": {
        "free": ["basic answers", "simple translations", "general knowledge"],
        "premium": ["deep reasoning", "long-form content", "advanced coding help"]
    }
}
musab_chatbot.add_modules(modules)

# Start the chatbot (simple HFA launch command)
musab_chatbot.launch(
    interface="web",         # or "api" for backend integration
    allow_free_users=True,   # Freemium setup
    theme="friendly"         # Visual theme (optional)
)

print("Musab Chatbot is live! 🌟 Ready to answer questions like ChatGPT with Gemini features.")

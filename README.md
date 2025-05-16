# speech-based-search-engine

---

## 🛠️ **Libraries Used**

* `speech_recognition` for converting speech to text
* `pyttsx3` for text-to-speech feedback
* `webbrowser` to open search results in the default browser

---

## 🔁 **Workflow Summary**

1. **Initialize TTS Engine**:

   ```python
   engine = pyttsx3.init()
   ```

2. **Speak Function** – Reads out any given text:

   ```python
   def speak(text):
       engine.say(text)
       engine.runAndWait()
   ```

3. **Take Command Function** – Captures voice input:

   * Prompts: *"What do you want to search for?"*
   * Listens through microphone
   * Converts voice to text using Google Speech Recognition API
   * Handles errors if nothing is heard or if the API fails

4. **Search Function** – Uses voice input as a search query:

   ```python
   def search_web(query):
       if query:
           url = f"https://www.google.com/search?q={query}"
           webbrowser.open(url)
           speak(f"Here are the search results for {query}")
       else:
           speak("No search query provided.")
   ```

5. **Main Execution**:

   ```python
   if __name__ == "__main__":
       query = take_command()
       search_web(query)
   ```

---

## ✅ **Usage**

Just run the script, speak your search query, and it will open Google search results in your browser.

---


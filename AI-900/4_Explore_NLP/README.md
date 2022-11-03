## Text Analytics Techniques
- Statistical analysis of terms used in the text.
- Extending frequency analysis to multi-term phrases, commonly known as N-grams.
- Applying stemming or lemmatization algorithms to normalize words before counting them.
- Applying linguistic structure rules to analyze sentences.
- Encoding words or terms as numeric features that can be used to train a machine learning model.
- Creating vectorized models that capture semantic relationships between words by assigning them to locations in n-dimensional space.

## Azure resources for the Language service
- A Language resource
- A Cognitive Services resource

### Language resource capabilities
- Language detection
- Sentiment analysis
- Key phrase extraction
- Entity recognition

## Azure resources for the Speech service
- The Speech-to-Text API
  - Real-time transcription: The audio source for transcription can be a real-time audio stream from a microphone or an audio file.    
  - Batch transcription: You can point to audio files with a shared access signature (SAS) URI and asynchronously receive transcription results.
- The Text-to-Speech API

## Translation in Azure
- The **Translator** service, which supports text-to-text translation.
- The **Speech** service, which enables speech-to-text and speech-to-speech translation.
  - Speech-to-text - used to transcribe speech from an audio source to text format.
  - Text-to-speech - used to generate spoken audio from a text source.
  - Speech Translation - used to translate speech in one language to text or speech in another.

## Conversational language understanding
On Microsoft Azure, conversational language understanding is supported through the **Language Service**. Three core concepts: 
- utterances
- entities
- intents

## Conversational AI
- A _knowledge base_ of question and answer pairs - usually with some built-in natural language processing model to enable questions that can be phrased in multiple ways to be understood with the same semantic meaning.
- A _bot service_ that provides an interface to the knowledge base through one or more channels.

Azure services
- Language service. The Language service includes a custom question answering feature that enables you to create a knowledge base of question and answer pairs that can be queried using natural language input.
- Azure Bot service. This service provides a framework for developing, publishing, and managing bots on Azure.


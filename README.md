# Conversation Management & Classification using Groq API

A comprehensive project demonstrating advanced conversation management and structured data extraction using the Groq API with OpenAI-compatible interfaces.

## 📋 Project Overview

This project consists of two main components:
1. **Conversation Management System** - Intelligent conversation history management with truncation and summarization
2. **JSON Schema Extraction System** - Structured data extraction from conversational text using function calling

## 🎯 Objectives

- **Task 1**: Implement conversation history management with multiple truncation strategies and periodic AI-powered summarization
- **Task 2**: Extract structured user information from conversations using JSON schema validation and Groq API function calling

## 📁 Project Structure

```
project-root/
├── notebooks/
│   ├── task1_conversation_management.ipynb
│   └── task2_json_extraction.ipynb
└── README.md
```

## 🚀 Getting Started

### Prerequisites

1. **Python 3.8+** - Standard Python installation
2. **Groq API Key** - Sign up at [Groq Console](https://console.groq.com/) to get your API key
3. **Google Colab Account** (optional) - For running notebooks in the cloud

### Required Dependencies

The notebooks use only standard Python libraries plus:
- `requests` - For HTTP API calls
- `openai` - Official OpenAI client library (Groq API is compatible)

### Installation

#### Option 1: Google Colab (Recommended)
1. Upload the notebook files to Google Colab
2. The notebooks will automatically install required dependencies
3. Set your Groq API key in the configuration cells

#### Option 2: Local Jupyter Environment
1. Clone or download this repository
2. Install dependencies:
   ```bash
   pip install openai requests jupyter
   ```
3. Set your Groq API key as an environment variable:
   ```bash
   export GROQ_API_KEY="your_groq_api_key_here"
   ```
4. Start Jupyter:
   ```bash
   jupyter notebook
   ```

## 🔧 Configuration

### API Key Setup

**Important**: You must configure your Groq API key before running the notebooks.

#### Method 1: Environment Variable (Recommended)
```bash
export GROQ_API_KEY="your_groq_api_key_here"
```

#### Method 2: Direct Assignment (Google Colab)
In the API configuration cells, uncomment and set:
```python
GROQ_API_KEY = "your_groq_api_key_here"
```

## 📓 Notebook Descriptions

### Task 1: Conversation Management (`task1_conversation_management.ipynb`)

**Purpose**: Demonstrates intelligent conversation history management with AI-powered summarization.

**Key Features**:
- ✅ **Multi-Strategy Truncation**: Limit by turns, words, or characters
- ✅ **Periodic Summarization**: Automatic conversation summarization using Groq API
- ✅ **Conversation Statistics**: Real-time monitoring of conversation metrics
- ✅ **Flexible Configuration**: Customizable truncation and summarization settings

**Demonstrations**:
1. Basic conversation management with turn limits
2. Word count-based truncation
3. Character count-based truncation  
4. Periodic AI summarization every N turns

**Use Cases**:
- Chatbot memory management
- Customer support ticket summarization
- Long conversation processing for LLMs
- Context window optimization

### Task 2: JSON Schema Extraction (`task2_json_extraction.ipynb`)

**Purpose**: Extracts structured user information from conversational text using function calling.

**Target Schema**:
```json
{
  "name": "string",
  "email": "string", 
  "phone": "string",
  "location": "string",
  "age": "integer"
}
```

**Key Features**:
- ✅ **Function Calling**: Uses Groq API's OpenAI-compatible function calling
- ✅ **Schema Validation**: Multi-level validation with regex patterns
- ✅ **Confidence Scoring**: Automatic confidence assessment
- ✅ **Error Handling**: Robust error handling and validation reporting

**Demonstrations**:
1. Complete user profile extraction
2. Partial information handling
3. Technical support ticket processing
4. Business inquiry information extraction
5. Real-time extraction testing

**Use Cases**:
- CRM data entry automation
- Lead qualification from chat logs
- Support ticket routing
- User profile enrichment

## 🏃‍♂️ How to Run

### Quick Start Guide

1. **Open a notebook** in Google Colab or Jupyter
2. **Install dependencies** by running the first code cell
3. **Configure API key** in the API configuration section
4. **Run all cells** to see complete demonstrations
5. **Experiment** with the interactive examples

### Running Specific Demonstrations

Each notebook is structured with clear sections:

#### Task 1 - Conversation Management:
- Run cells sequentially for complete demonstration
- Modify `ConversationManager` parameters to test different settings
- Try your own conversation samples in the demonstration sections

#### Task 2 - JSON Extraction:
- Process the provided sample conversations
- Test with custom conversations in the real-time section
- Review validation reports and performance analysis

## 🧪 Sample Outputs

### Task 1 - Conversation Management
```
📋 CURRENT CONVERSATION HISTORY
==================================================
1. 👤 USER: Hi, I'm looking for help with Python...
2. 🤖 ASSISTANT: Hello! I'd be happy to help you...
3. ⚙️ SYSTEM: Previous conversation summary: User inquired about Python programming...

📊 STATISTICS
  total_turns: 8
  current_messages: 3
  total_words: 156
  summaries_created: 2
```

### Task 2 - JSON Extraction
```json
{
  "extracted_data": {
    "name": "Sarah Johnson",
    "email": "sarah.johnson@email.com", 
    "phone": "(555) 123-4567",
    "location": "Seattle, Washington",
    "age": 28,
    "confidence_score": 1.0
  },
  "validation": {
    "is_valid": true,
    "errors": [],
    "warnings": []
  }
}
```

## 🔍 Key Technical Features

### Conversation Management
- **Memory Efficiency**: Prevents unbounded conversation growth
- **Context Preservation**: AI summarization maintains conversation context  
- **Flexible Truncation**: Multiple strategies (turns, words, characters)
- **Production Ready**: Comprehensive error handling and monitoring

### JSON Schema Extraction  
- **Function Calling**: Leverages Groq API's structured output capabilities
- **Multi-Level Validation**: Schema compliance, format validation, business rules
- **Performance Monitoring**: Success rates, field extraction statistics
- **Extensible Architecture**: Easy to add new fields and validation rules

## 🛠️ Customization

### Adding New Truncation Strategies
Extend the `ConversationManager` class with custom truncation logic:

```python
def _truncate_by_custom_rule(self):
    # Your custom truncation logic here
    pass
```

### Extending JSON Schema
Add new fields to the schema in `task2_json_extraction.ipynb`:

```python
USER_INFO_SCHEMA["properties"]["new_field"] = {
    "type": "string",
    "description": "Description of new field"
}
```

## ⚡ Performance & Scaling

- **API Efficiency**: Optimized API calls with proper error handling
- **Memory Management**: Efficient conversation truncation prevents memory bloat
- **Concurrent Processing**: Architecture supports batch processing
- **Rate Limiting**: Built-in retry logic for API rate limits

## 🐛 Troubleshooting

### Common Issues

**API Key Errors**:
- Ensure your Groq API key is correctly set
- Check API key permissions and credits

**Import Errors**:
- Run the pip install cells in the notebooks
- Restart kernel if dependencies don't load properly

**Function Calling Errors**:
- Verify Groq API supports function calling for your model
- Check function schema format matches OpenAI specifications

**Memory Issues**:
- Use truncation settings to limit conversation history size
- Process conversations in smaller batches for large datasets

## 🤝 Contributing

This is an educational project. Feel free to:
- Experiment with different API models
- Add new validation rules
- Extend the schema with additional fields
- Test with different conversation types

## 📄 License

This project is provided for educational purposes. Please ensure compliance with Groq API terms of service when using their API.

## 🔗 Resources

- [Groq Console](https://console.groq.com/) - Get your API key
- [Groq Documentation](https://console.groq.com/docs) - API documentation  
- [OpenAI Function Calling](https://platform.openai.com/docs/guides/function-calling) - Function calling guide
- [JSON Schema Validation](https://json-schema.org/) - Schema specification

---

**Happy Coding!** 🚀

For questions or issues, please review the troubleshooting section or check the Groq API documentation.
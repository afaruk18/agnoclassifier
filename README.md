An AI-powered system for automatically classifying Turkish legal documents into predefined contract categories using OpenAI's GPT models and the Agno framework.



    Automated Classification: Classifies Turkish legal documents into 20 predefined contract types
    
    PDF Support: Extracts text from PDF files and processes them for classification
    
    Memory & Storage: Optional memory and storage capabilities for maintaining conversation history
    
    Confidence Scoring: Provides relevance scores for all contract categories with detailed rationales
    
    Key Term Extraction: Identifies important legal terms that support the classification decision
    
    Configurable: Customizable model selection, memory settings, and classification parameters

Supported Contract Types

The classifier can identify the following Turkish legal contract types(Default,can be changed):

    Hizmet Sözleşmesi (Service Contract)
    İş Sözleşmesi (Employment Contract)
    Sigorta Sözleşmesi (Insurance Contract)
    Kira Sözleşmesi (Rental Contract)
    Gizlilik Sözleşmesi (NDA)
    Lisans Sözleşmesi (License Agreement)
    Franchise Sözleşmesi (Franchise Agreement)
    Distribütörlük Sözleşmesi (Distribution Agreement)
    Ortaklık Sözleşmesi (Partnership Agreement)
    Teminat Sözleşmesi (Guarantee Contract)
    Taşeronluk Sözleşmesi (Subcontract Agreement)
    İpotek Sözleşmesi (Mortgage Contract)
    Tedarik Sözleşmesi (Supply Contract)
    Yatırım Sözleşmesi (Investment Agreement)
    Danışmanlık Sözleşmesi (Consulting Agreement)
    Alım Satım Sözleşmesi (Purchase Agreement)
    Acentelik Sözleşmesi (Agency Agreement)
    Kefalet Sözleşmesi (Surety Contract)
    Gayrimenkul Satış Sözleşmesi (Real Estate Sales Contract)
    Teknoloji Transfer Sözleşmesi (Technology Transfer Agreement)

Installation

Required Dependencies

bash

    uv add agno
    uv add langchain-community
    uv add pydantic
    uv add python-dotenv


Usage
Basic Usage

python

    from agno_classifier.legal_classifier import LegalDocumentClassifier
    from dotenv import load_dotenv

    # Load environment variables
    load_dotenv()

    # Create classifier instance
    classifier = LegalDocumentClassifier(
        model_id="gpt-4.1-nano",
        user_id="your_user_id",
        db_file="tmp/memory.db",
        debug_mode=True
    )

    # Classify a PDF document
    pdf_path = "path/to/your/document.pdf"
    result = classifier.get_response_and_scores(pdf_file_path)
    print("Classification Result:", result)



# Custom configuration
classifier = LegalDocumentClassifier(
    model_id="gpt-4o",  # Different model
    user_id="custom_user",
    db_file="custom/path/memory.db",
    max_chars_for_prompt=8000,  # Larger prompt size
    enable_memory=True,
    enable_storage=True,
    debug_mode=False
)

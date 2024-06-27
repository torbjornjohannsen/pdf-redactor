# PDFRedactor

PDFRedactor is a Python tool for redacting sensitive information from PDF files. The script can detect and redact phone numbers, email addresses, links, IBANs, BICs, timestamps, dates, and custom text patterns from PDF documents.

## Features

- **Phone Numbers**: Redact all detected phone numbers.
- **Email Addresses**: Redact all detected email addresses.
- **Links**: Redact all detected links.
- **IBANs**: Redact all detected International Bank Account Numbers.
- **BICs**: Redact all detected Bank Identifier Codes.
- **Timestamps**: Redact all detected timestamps.
- **Dates**: Redact all detected dates in various formats.
- **Custom Text Patterns**: Redact any custom text pattern specified by the user.

## Installation

To install PDFRedactor, follow these steps:

1. Clone the repository:

   ```bash
   git clone https://github.com/ltillmann/pdf-redactor.git

2. Move to the directory

3. Install the required dependencies using pip:
   
   ```bash
   pip install -r requirements.txt

## Usage

You can run the script from the command line. Below are the available options:
 
   ```bash
   pdf_redactor.py [-h] -i INPUT [-e] [-l] [-p] [-v] [-m MASK] [-t TEXT]
                   [-c {white,black,red,green,blue}] [-d] [-f] [-s] [-b]

### Options:

- `-h`, `--help`: Show help message and exit.
- `-i INPUT`, `--input INPUT`: Filename to be processed.
- `-e`, `--email`: Redact all email addresses.
- `-l`, `--link`: Redact all links.
- `-p`, `--phonenumber`: Redact all phone numbers.
- `-v`, `--preview`: Preview redacted areas before continuing.
- `-m MASK`, `--mask MASK`: Custom Word mask to redact, e.g. "John Doe" (case insensitive).
- `-t TEXT`, `--text TEXT`: Text to show in redacted areas. Default: None.
- `-c {white,black,red,green,blue}`, `--color {white,black,red,green,blue}`: Fill Color of redacted areas. Default: "black".
- `-d`, `--date`: Redact all dates (dd./-mm./-yyyy).
- `-f`, `--timestamp`: Redact all timestamps.
- `-s`, `--iban`: Redact all IBANs (International Bank Account Numbers).
- `-b`, `--bic`: Redact all BICs (Bank Identifier Codes).

## Examples

1. Redact phone numbers from a single PDF file:
   
   ```bash
   python pdf_redactor.py -i input_file.pdf -p

2. To redact email addresses and preview redacted areas:

   ```bash
   python pdf_redactor.py -i input_file.pdf -e -v

3. Redact custom text patterns and specify redaction text from directory of files:

   ```bash
   python pdf_redactor.py -i directory_path -m "CONFIDENTIAL" -t "[REDACTED]"

## Preview Redactions

When using the `-v` or `--preview` option, the script will display a preview of the redacted areas on each page and prompt you to continue with the redaction or abort.

## License

This project is licensed under the MIT License.

## Acknowledgments

- This tool utilizes the PyMuPDF library for OCR and PDF processing [PyMuPDF](https://github.com/pymupdf/PyMuPDF).
- To match phone numbers, I used David Drysdales Python port of Google's libphonenumber [python-phonenumbers](https://github.com/daviddrysdale/python-phonenumbers)

## Contributing

Contributions are welcome! Please feel free to open a pull request or report issues.





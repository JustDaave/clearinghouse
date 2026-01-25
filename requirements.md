Semester Project Requirements Document


Project Title

Hex Payment Gateway – Credit Card Processing Clearinghouse API

Developer Name

David Dipalo-Gross

Business Context

The primary business driver for this project is the need for a fast, reliable, and accurate credit card transaction clearinghouse that can act as an intermediary between merchants and card-issuing banks. Merchants require immediate feedback on whether a transaction is approved or declined so they can complete or cancel a purchase without delaying the customer experience. The system must prioritize low latency, correctness, and availability while handling high transaction volumes.

Description of the Domain

This system operates in the payment processing domain, specifically as a simulated credit card transaction clearinghouse. Merchants (such as retail stores) submit transaction requests to the clearinghouse API after a customer swipes or enters their card information. The clearinghouse validates the request, determines which bank or card provider should handle the transaction, forwards the request to the appropriate simulated bank API, and returns an approval or denial to the merchant. Primary users include merchant systems, simulated bank systems, and system administrators.

Problem Statement

Merchants need a centralized and consistent way to process credit card transactions without directly integrating with multiple bank or card provider APIs. Without such a system, merchants face increased complexity, slower response times, and higher risk of errors. The solution must provide a single, reliable interface that handles transaction routing, validation, and response delivery quickly and accurately.

Scope

In Scope

A REST-based API that accepts credit card transaction requests from merchants

Validation of incoming transaction data

Routing transactions to the appropriate simulated bank or card provider

Logging of transaction activity for auditing and troubleshooting

Returning approval or denial responses to merchants

Out of Scope / Future Enhancements

Use of real credit card numbers or real financial institutions

Actual transfer of money

Customer-facing user interfaces

Fraud detection and advanced risk scoring (future release)

Merchant onboarding dashboards (future release)

Functional Requirements

The system shall expose an API endpoint for merchants to submit credit card transaction requests.

The system shall accept transaction details including amount, merchant ID, card number, expiration date, and card type.

The system shall validate that all required transaction fields are present in the request.

The system shall reject transactions with missing or malformed data.

The system shall identify the card issuer or bank based on the card information provided.

The system shall route the transaction request to the appropriate simulated bank or card provider API.

The system shall record each transaction request in a transaction log.

The system shall record the response received from the bank or card provider.

The system shall return an “approved” response to the merchant when the bank approves the transaction.

The system shall return a “declined” response to the merchant when the bank denies the transaction.

The system shall return an error response if the bank or card provider is unavailable.

The system shall generate a unique transaction ID for each request.

The system shall include the transaction ID in all responses to the merchant.

The system shall support multiple simulated bank or card provider integrations.

The system shall process transactions independently so one failed transaction does not affect others.

The system shall allow configuration of supported card types.

The system shall provide clear response codes indicating success, denial, or error.

The system shall reject duplicate transaction requests using the same transaction ID.

Non-Functional Requirements

The system shall be available at least 99.9% of the time.

The system shall respond to merchant transaction requests within 2 seconds under normal load.

The system shall support at least 1,000 transactions per minute.

The system shall scale horizontally to support increased transaction volume.

The system shall log all transactions in a secure and tamper-resistant manner.

The system shall not store real credit card numbers.

The system shall restrict API access to authenticated merchant clients.

The system shall encrypt all data in transit.

The system shall provide clear error messages without exposing sensitive system details.

The system shall be deployable in an AWS environment.

The system shall be resilient to partial failures of external bank APIs.

The system shall allow administrators to review transaction logs.

The system shall maintain consistent behavior across environments (development, test, production).

# Omnio Liveliness Credential Schema (v1.0)

Liveliness Credential issued by **Omnio** (via Fidociary) represents the result of a liveliness check for a subject identified by a DID.

## @context

Defines the JSON-LD context that provides semantic meaning to the credential.

```json
"@context": "https://example.com/path/to/file/context.jsonld"
```

---

## id

The unique identifier of the credential.

```json
"id": "<did of the user>"
```

---

## type

Defines the type of the credential. This can be a single string or an array of types.

```json
"type": ["VerifiableCredential", "LivelinessCredential"]
```

---

## issuer

The DID of the entity (issuer) that issues the credential. It can also be a detailed object containing metadata.

```json
"issuer": {
  "id": "<did of the issuer>"
}
```

---

## issuanceDate

The date and time when the credential was issued (ISO 8601 format).

```json
"issuanceDate": "2025-04-23T12:00:00Z"
```

---

## expirationDate (optional)

The date and time when the credential expires (if any).

```json
"expirationDate": "2026-04-23T12:00:00Z"
```

---

## credentialSchema

Points to the schema that defines the structure and semantics of the credential.

```json
"credentialSchema": {
  "id": "https://example.com/schemas/liveliness.json",
  "type": "JsonSchemaValidator2020"
}
```

---

## credentialStatus (optional but recommended)

Contains status information like suspension or revocation of the credential.

```json
"credentialStatus": {
  "id": "https://example.com/status/12345",
  "type": "CredentialStatusList2021"
}
```

---

## credentialSubject

The entity the credential is about. In this case, the subject being verified for liveliness.

### id

DID of the credential subject.

```json
"id": "did:example:subject456"
```

### verified

Boolean indicating the result of the liveliness check (e.g., from a facial scan or similar proof of presence).

```json
"verified": true
```
# Architecture (proposed vs current demo)

Buyer / Seller App → API & Workflow Service → Drunix Contract / Shared Ledger → Regulated Partner Adapter → Bank / UPI / IMPS

Courier evidence adapter → Verification service → Workflow rules. Partner confirmations → Reconciliation and audit history.

## Drunix (proposed)
Shared order terms, permissioned organization identities, evidence hashes, release decisions and endorsement policy, cross-organization audit trail.

## Off-chain (proposed)
Raw proof documents, customer information, courier verification, fiat custody and bank payments, reconciliation. Raw personal data and delivery documents never go on the shared ledger; only references and evidence hashes.

## Current demo
Local browser app, simulated organization roles, mock courier and bank events, local workflow and audit storage. No live Drunix network, smart contract, or NPCI API connection exists.

## Why a shared ledger
Buyer, seller and payment partner can use a jointly governed record of agreed terms and decisions instead of relying entirely on one company's editable database. A ledger cannot establish whether physical goods were delivered correctly; evidence quality, governance and dispute resolution remain essential.

## Needed for production
Regulated partner agreement for custody; real UPI/IMPS or bank integration (ordinary UPI is not programmable escrow); verified courier integrations; real authentication; agreed dispute authority, evidence standards and time limits; security, compliance and legal review.

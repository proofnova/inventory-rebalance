# Inventory rebalance solver

여러 거점의 초과·부족 재고를 이동 한도 안에서 전역 최소 비용으로 재배치한다.

A focused executable resource for AI-assisted structured work. **Zero runtime dependencies, no API key, Node.js 22+.**

[Live workspace](https://proofnova.github.io/inventory-rebalance/) · [한국어 리소스 모음](https://proofnova.github.io/) · [Task contract](resource.json) · [Prior art](RESEARCH.md)

```sh
git clone https://github.com/proofnova/inventory-rebalance.git
cd inventory-rebalance
npm test
node cli.mjs example.json
```

## What it does

Residual-network min-cost flow that can undo a locally cheap assignment.

A greedy route choice can be globally worse; supply, demand and route capacities must be conserved.

## Connect a model

Import `execute` from `./run.mjs`. Expose this declared tool to your model, validate its tool name/input contract, execute it, and retain the returned JSON and input digest. Calculations and constraint checks are performed by the resource. No paid model or new agent framework is required.

[SKILL.md](SKILL.md) contains the workflow, interpretation and recovery procedure. [example.json](example.json) is a complete input; [cases.json](cases.json) contains worked and held-out synthetic checks. The website executes the same code locally in a bounded Worker. It has no model or external data upload.

## Recovery and limits

Inspect unresolved shortages or add a route/capacity; no actual order or transfer is submitted.

Underlying algorithms and task outcomes already exist in the alternatives. An existing tool configured for this exact task may remove the need for a separate project. Small synthetic tests cannot establish broad expertise or external demand. See [RESEARCH.md](RESEARCH.md). A plan/audit is not an external action or proof of actual user benefit.

## Contribute

Open an issue with a synthetic/redacted failing JSON input, expected result and Node version. Add a regression test and run `npm test`. Never include credentials or real private records in public examples.

MIT · Proofnova · 2026

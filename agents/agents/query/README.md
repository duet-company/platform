# Query Agent

Natural language to SQL translation for AI Data Labs.

## 🎯 Purpose

Transforms natural language queries into optimized SQL for ClickHouse and PostgreSQL.

## 🚀 Features

- NL to SQL translation
- Query optimization
- Result visualization
- Error handling and correction

## 🧠 Models

Supports multiple LLM providers:
- Claude (Anthropic)
- GPT-4 (OpenAI)
- GLM-5 (Z.AI)

## 🔗 Integration

- **Backend:** https://github.com/duet-company/backend
- **Platform:** https://github.com/duet-company/platform
- **Docs:** https://github.com/duet-company/docs

## 📖 Usage

```python
from agents.query import QueryAgent

agent = QueryAgent(model="claude-3-opus")
result = agent.query("Show me revenue trends for last 6 months")
print(result.sql)  # Generated SQL
print(result.visualization)  # Chart data
```

## 🧪 Testing

```bash
# Run tests
pytest tests/

# Run with specific model
MODEL=gpt-4 pytest tests/
```

## 📚 Resources

- [LLM Integration Guide](../../docs/guides/llm-integration.md)
- [ClickHouse SQL Reference](https://clickhouse.com/docs/en/sql-reference/)
- [Query Optimization](../../docs/guides/query-optimization.md)

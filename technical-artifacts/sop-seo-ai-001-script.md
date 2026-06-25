---
layout: default
title: SOP-SEO-AI-001 Programmatic Validation Script
---

<div class="container" style="max-width: 900px; margin: 0 auto; padding: 40px 20px;">
  <div style="margin-bottom: 30px;">
    <a href="/technical-artifacts" style="text-decoration: none; color: #2563EB; font-weight: 500; display: inline-flex; align-items: center; gap: 5px;">
      ← Back to Technical Artifacts
    </a>
  </div>

  <header style="border-bottom: 1px solid #E2E8F0; padding-bottom: 25px; margin-bottom: 35px;">
    <span style="color: #64748B; font-family: monospace; font-size: 0.9rem; text-transform: uppercase; letter-spacing: 0.05em;">Technical Case Study // Companion Artifact</span>
    <h1 style="font-size: 2.25rem; color: #0F172A; margin-top: 5px; margin-bottom: 15px; font-weight: 700;">
      SOP-SEO-AI-001: Programmatic Adversarial Validation Script
    </h1>
    <p style="color: #475569; font-size: 1.1rem; line-height: 1.6; margin: 0;">
      This standalone Python module provides the defensive automation engine specified in <strong>Section 6.1 (Step 2 & 3)</strong> of the Zero-Trust AI Integration Standard. It intercepts raw LLM outputs, enforces strict structural type-coercion against a ground-truth dictionary schema, and safely routes exceptions to an isolated quarantine pipeline to prevent database contamination.
    </p>
  </header>

  <section style="margin-bottom: 40px;">
    <h3 style="font-size: 1.3rem; color: #1E293B; margin-bottom: 15px;">Core Execution Logic</h3>
    <ul style="color: #475569; line-height: 1.6; padding-left: 20px;">
      <li style="margin-bottom: 10px;"><strong>Layer 1 (Structural Integrity):</strong> Parses raw string arrays using <code>json.loads()</code> to catch incomplete tokens, trailing whitespaces, or truncated API strings.</li>
      <li style="margin-bottom: 10px;"><strong>Layer 2 (Schema Enforcement):</strong> Iterates through the master dictionary keys to intercept missing metrics or incorrect data formats.</li>
      <li style="margin-bottom: 10px;"><strong>Type Coercion Buffer:</strong> Gracefully converts rigid integer inputs into required float decimals to prevent unneeded routing errors.</li>
      <li style="margin-bottom: 10px;"><strong>Deterministic Quarantine:</strong> Intercepts any single validation failure instantly, halting forward execution to wrap the corrupted payload in an isolated diagnostic block for manual review.</li>
    </ul>
  </section>

<section id="source-code" style="margin-top: 30px;">
    <h3 style="font-size: 1.3rem; color: #1E293B; margin-bottom: 20px; font-family: monospace;">Python Implementation & Test Harness</h3>

    {% highlight python %}
import json
import logging
from datetime import datetime

# Initialize diagnostic exception logging
logging.basicConfig(level=logging.INFO, format='%(asctime)s - %(levelname)s - %(message)s')

# Define the Master Expected Schema
EXPECTED_SCHEMA = {
    "target_keyword": str,
    "search_volume": int,
    "difficulty_score": float,
    "optimized_title": str
}

def validate_ai_payload(raw_json_payload: str) -> dict:
    """
    Ingests a raw AI payload, runs adversarial schema tests,
    and returns verified data or routes exceptions to quarantine.
    """
    try:
        # Step 1: Parse string to JSON
        parsed_data = json.loads(raw_json_payload)
        
        # Step 2: Adversarial Schema Verification Gate
        validated_payload = {}
        for key, expected_type in EXPECTED_SCHEMA.items():
            if key not in parsed_data:
                raise KeyError(f"CRITICAL DRIFT: Missing required column/key: '{key}'")
            
            actual_value = parsed_data[key]
            
            # Handle potential numeric type conversions
            if expected_type == float and isinstance(actual_value, int):
                actual_value = float(actual_value)
                
            if not isinstance(actual_value, expected_type):
                raise TypeError(
                    f"TYPE MISMATCH: Key '{key}' expected {expected_type.__name__}, "
                    f"received {type(actual_value).__name__} ('{actual_value}')"
                )
                
            validated_payload[key] = actual_value
            
        logging.info("PAYLOAD SUCCESS: Passed Layer 1 and Layer 2 validation gates.")
        return {"status": "STAGING_READY", "data": validated_payload}
        
    except (json.JSONDecodeError, KeyError, TypeError) as e:
        # Step 3: Exception Routing & Quarantine Isolation
        quarantine_error_log = {
            "timestamp": datetime.utcnow().isoformat(),
            "error_type": type(e).__name__,
            "diagnostic_message": str(e),
            "corrupted_payload": raw_json_payload
        }
        
        logging.error(f"EXCEPTION TRIGGERED: Payload quarantined. Message: {str(e)}")
        return {"status": "QUARANTINED", "error_log": quarantine_error_log}

# ==========================================
# SYSTEM VALIDATION TEST RUNS
# ==========================================

if __name__ == "__main__":
    # Test 1: Flawless, conforming data payload
    good_payload = '{"target_keyword": "technical seo architect", "search_volume": 1200, "difficulty_score": 45.5, "optimized_title": "Mastering the Technical SEO Architect Role"}'
    print("--- Running Test 1: Valid Data ---")
    print(json.dumps(validate_ai_payload(good_payload), indent=2))

    # Test 2: Corrupted data payload (Structural Drift / Missing Key)
    bad_payload = '{"target_keyword": "data analytics automation", "difficulty_score": "high", "optimized_title": "Automating Data Streams"}'
    print("\n--- Running Test 2: Invalid Data (Triggers Exception Routing) ---")
    print(json.dumps(validate_ai_payload(bad_payload), indent=2))
    {% endhighlight %}
  </section>
</div>  
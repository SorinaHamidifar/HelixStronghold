# ================================
# Project: FortressCore
# Description:
# A fortified hub for complex logic, system designs,
# and durable software foundations.
# ================================

# ---------- main.py ----------
"""
Main entry point for FortressCore.
"""

from core.logic import DecisionEngine
from core.system import SystemBlueprint//


def run():
    print("🛡️ FortressCore Online")
    print("🏗️ System Design | 🧠 Complex Logic | 🧱 Durable Foundations\n")

    engine = DecisionEngine()
    system = SystemBlueprint()

    data = [12, 18, 25, 40]

    print("🧠 Decision Result:", engine.evaluate(data))
    print("🏗️ System Integrity:", system.integrity_check(data))
    print("📈 Capacity Projection:", system.capacity_forecast(base=200, growth=0.12))


if __name__ == "__main__":
    run()


# ---------- core/logic.py ----------
"""
Core logic layer for complex decision-making and rule evaluation.
"""

import statistics

class DecisionEngine:
    """Handles complex logic and rule-based evaluations."""

    def evaluate(self, values):
        """Evaluate data and return a logical decision."""
        if not values:
            return "NO DATA"

        avg = statistics.mean(values)
        spread = statistics.pstdev(values)

        if avg > 30 and spread < 10:
            return "OPTIMAL"
        elif avg > 20:
            return "ACCEPTABLE"
        else:
            return "RISKY"


# ---------- core/system.py ----------
"""
System architecture and durability utilities.
"""

class SystemBlueprint:
    """Defines system structure, stability, and long-term durability."""

    def integrity_check(self, values):
        """Assess structural integrity based on consistency."""
        if not values:
            return "UNKNOWN"

        max_val = max(values)
        min_val = min(values)

        if max_val - min_val < 20:
            return "STABLE 🧱"
        return "STRAINED ⚠️"

    def capacity_forecast(self, base: int, growth: float, years: int = 4) -> int:
        """Forecast system capacity growth over time."""
        return int(base * ((1 + growth) ** years))


# ---------- tests/test_logic.py ----------
"""
Tests for complex logic engine.
"""

from core.logic import DecisionEngine

def test_evaluate():
    engine = DecisionEngine()
    assert engine.evaluate([30, 32, 31]) == "OPTIMAL"
    assert engine.evaluate([10, 15]) == "RISKY"


# ---------- tests/test_system.py ----------
"""
Tests for system blueprint.
"""

from core.system import SystemBlueprint

def test_integrity_check():
    system = SystemBlueprint()
    assert system.integrity_check([10, 12, 14]) == "STABLE 🧱"

def test_capacity_forecast():
    system = SystemBlueprint()
    assert system.capacity_forecast(100, 0.1, years=2) > 100


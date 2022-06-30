# Input validation

Having an input validation framework is an excellent way to prevent all kinds of zero-day exploits — not just SQL injection.
Single quotes or semicolons in a credit card number or numeric user ID are really not needed.
Better yet, base validation on a whitelist: accept data fitting a specified structure, instead of rejecting patterns. 

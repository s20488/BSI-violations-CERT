# BSI-violations-CERT by Anastasiia Ponkratova, Julia Migiel

### ProhibitedBrandsServiceImpl
    In this case, compliance with OBJ10-J (Do not use public static nonfinal fields) from CERT-J classification was required. We implemented the following solution:
    
#### Compliant Solution
    This compliant solution declares the FuncLoader static field final and treats it as a constant:
    public static final FuncLoader m_functions;
    // Initialize m_functions in a static initialization block

### FileCopyUtils
    In this case, if a closure error occurs, the output will not be closed.
    According to FIO14-J (Perform proper cleanup at program termination) from the CERT-J classification, we applied the "Compliant Solution (close())" in a broader scope to ensure everything is closed regardless of the type of error.

### ValueDao
    In this case, it was necessary to follow IDS00-J (Prevent SQL injection) from the CERT-J classification.
    For the solution, we used the following example:

#### Compliant Solution (PreparedStatement)
    The JDBC library provides an API for building SQL commands that sanitize untrusted data. The java.sql.PreparedStatement class properly escapes input strings, preventing SQL injection when used correctly. 

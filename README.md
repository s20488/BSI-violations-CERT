# BSI_violations_CERT by Anastasiia Ponkratova, Julia Migiel


### ProhibitedBrandsServiceImpl
    W tym przypadku należalo zastosowac się do OBJ10-J. (Do not use public static nonfinal fields) klasyfikacji CERT-J. Do rozwiązania użyliśmy przykładu:
    
#### Compliant Solution

    This compliant solution declares the FuncLoader static field final and treats it as a constant:
    public static final FuncLoader m_functions;
    // Initialize m_functions in a static initialization block


### FileCopyUtils
    W tym przypadku jeśli wystąpi błąd zamykania, wyjście nie będzie zamknięte.
    Zgodnie z FIO14-J (Perform proper cleanup at program termination) z klasyfikacji CERT-J zastosowaliśmy "Compliant Solution (close())" w szerszym spektrum by bez względu na rodzaj błędu wszystko zostało zamknięte.

### ValueDao
    W tym przypadku należało zastosować się do IDS00-J (Prevent SQL injection)z klasyfikacji CERT-J.
    Do rozwiązania użyliśmy przykładu:

#### Compliant Solution (PreparedStatement)

    The JDBC library provides an API for building SQL commands that sanitize untrusted data. The java.sql.PreparedStatement class properly escapes input strings, preventing SQL injection when used correctly. 

### Generate certificates

    step certificate create root.linkerd.cluster.local root.crt root.key \
    --profile root-ca --no-password --insecure

### Generate the issuer credentials using the trust anchor

    step certificate create identity.linkerd.cluster.local issuer.crt issuer.key \
    --profile intermediate-ca --not-after 8760h --no-password --insecure \
    --ca root.crt --ca-key root.key

    cd ..
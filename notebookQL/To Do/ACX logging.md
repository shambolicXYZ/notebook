
**HERE Local Logging Config**

`set system syslog user * any emergency`

`set system syslog file messages any notice`
`set system syslog file messages authorization info`

`set system syslog file interactive-commands interactive-commands any`

`set system syslog file default-log-messages any info`
`set system syslog file default-log-messages match "(FRU Offline)|(FRU Online)|(FRU insertion)|(FRU power)|(FRU removal)|(commit complete)|(copying configuration to juniper.save)|(license add)|(license delete)|(link UP)|(package -X delete)|(package -X update)|(plugged in)|(requested 'commit' operation)|(unplugged)|Transferred|ifAdminStatus|transfer-file|transitioned| LFMD_3AH | RPD_MPLS_PATH_BFD|(Backup changed)|(Backup detected)|(Master Changed, Members Changed)|(Master Detected, Members Changed)|(Master Unchanged, Members Changed)|(Master changed)|(Master detected)|(interface vcp-)|(vc add)|(vc delete)|CFMD_CCM_DEFECT|(AIS_DATA_AVAILABLE)"`
`set system syslog file default-log-messages structured-data`
`set system syslog time-format year`
`set system syslog time-format millisecond`


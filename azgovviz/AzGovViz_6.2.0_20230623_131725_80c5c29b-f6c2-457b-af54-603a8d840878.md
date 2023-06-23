# Azure Governance Visualizer - Management Group Hierarchy

23-Jun-2023 13:17:25 (Eastern Standard Time)

## HierarchyMap (Mermaid)

::: mermaid
    graph TD;
TenantRoot("TenantRoot") --> 80c5c29b-f6c2-457b-af54-603a8d840878("Tenant Root Group<br/>80c5c29b-f6c2-457b-af54-603a8d840878")
80c5c29b-f6c2-457b-af54-603a8d840878("Tenant Root Group<br/>80c5c29b-f6c2-457b-af54-603a8d840878") --> az104-02-mg1("az104-02-mg1")
80c5c29b-f6c2-457b-af54-603a8d840878("Tenant Root Group<br/>80c5c29b-f6c2-457b-af54-603a8d840878") --> az104-02-mg11("az104-02-mg11")

80c5c29b-f6c2-457b-af54-603a8d840878("Tenant Root Group<br/>80c5c29b-f6c2-457b-af54-603a8d840878") --> SubsOf80c5c29b-f6c2-457b-af54-603a8d840878("6")

 classDef mgr fill:#D9F0FF,stroke:#56595E,color:#000000,stroke-width:1px;
 classDef subs fill:#EEEEEE,stroke:#56595E,color:#000000,stroke-width:1px; classDef mgrprnts fill:#FFFFFF,stroke:#56595E,color:#000000,stroke-width:1px;
 class 80c5c29b-f6c2-457b-af54-603a8d840878,az104-02-mg1,az104-02-mg11 mgr;
 class SubsOf80c5c29b-f6c2-457b-af54-603a8d840878 subs;class ''80c5c29b-f6c2-457b-af54-603a8d840878'','80c5c29b-f6c2-457b-af54-603a8d840878' mgrprnts;
:::
## Summary

Total Management Groups: 3 (depth 1)\
Total Subscriptions: 6\
Total Custom Policy definitions: 17\
Total Custom PolicySet definitions: 0\
Total Policy assignments: 37\
Total Policy assignments ManagementGroups 0\
Total Policy assignments Subscriptions 12\
Total Policy assignments ResourceGroups: 25\
Total Custom Role definitions: 22\
Total Role assignments: 286\
Total Role assignments (Tenant): 4\
Total Role assignments (ManagementGroups): 4\
Total Role assignments (Subscriptions): 53\
Total Role assignments (ResourceGroups and Resources): 225\
Total Blueprint definitions: 1\
Total Blueprint assignments: 0\
Total Resources: 573\
Total Resource Types: 61

## Hierarchy Table

| **MgLevel** | **MgName** | **MgId** | **MgParentName** | **MgParentId** | **SubName** | **SubId** |
|-------------|-------------|-------------|-------------|-------------|-------------|-------------|
| 0 | Tenant Root Group | 80c5c29b-f6c2-457b-af54-603a8d840878 | TenantRoot | TenantRoot | SMX-SOUTHCOM-SRH-Sandbox | 6d0357ab-dd3d-4ab9-ac82-c08def70e813 |
| 0 | Tenant Root Group | 80c5c29b-f6c2-457b-af54-603a8d840878 | TenantRoot | TenantRoot | Pond Hop Demo | 722b67c0-5e76-40fa-811c-791e385a08b8 |
| 0 | Tenant Root Group | 80c5c29b-f6c2-457b-af54-603a8d840878 | TenantRoot | TenantRoot | MTN Demo | 964c406a-1019-48d1-a927-9461123de233 |
| 0 | Tenant Root Group | 80c5c29b-f6c2-457b-af54-603a8d840878 | TenantRoot | TenantRoot | MTNNet Main Subscription | a3ad3fff-f3c5-46cf-ac18-d384307648f8 |
| 0 | Tenant Root Group | 80c5c29b-f6c2-457b-af54-603a8d840878 | TenantRoot | TenantRoot | MTN Training | c7c39807-92fa-4bcb-8d7f-a604845698d0 |
| 0 | Tenant Root Group | 80c5c29b-f6c2-457b-af54-603a8d840878 | TenantRoot | TenantRoot | Partner Scratch Space | f5b490b4-4ce4-469b-9f14-32b600fd3959 |
| 1 | az104-02-mg1 | az104-02-mg1 | Tenant Root Group | 80c5c29b-f6c2-457b-af54-603a8d840878 | none | none |
| 1 | az104-02-mg11 | az104-02-mg11 | Tenant Root Group | 80c5c29b-f6c2-457b-af54-603a8d840878 | none | none |


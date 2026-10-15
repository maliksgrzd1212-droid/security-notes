# Şəbəkə əsasları: qısa qeydlər

## Subnetting
| Prefiks | Maska | Ümumi ünvan | Host |
|---------|-------|-------------|------|
| /24 | 255.255.255.0 | 256 | 254 |
| /25 | 255.255.255.128 | 128 | 126 |
| /26 | 255.255.255.192 | 64 | 62 |
| /27 | 255.255.255.224 | 32 | 30 |
| /28 | 255.255.255.240 | 16 | 14 |
| /30 | 255.255.255.252 | 4 | 2 |

Formul: `host sayı = 2^(32 - prefiks) - 2`

## DHCP (DORA)
Discover → Offer → Request → Acknowledge

## NAT vs PAT
- **NAT:** private IP → public IP çevirməsi
- **PAT:** bir public IP + fərqli portlar ilə çoxlu cihaz

## VLAN
Fiziki şəbəkəni məntiqi seqmentlərə bölür. VLAN-lar arasında trafik üçün L3 (router/L3 switch) lazımdır.

## Troubleshooting (aşağıdan yuxarıya)
Fiziki bağlantı → IP konfiqurasiya → gateway ping → xarici IP ping → DNS (`nslookup`) → `traceroute` → firewall/ACL

## Cisco əmrləri
```
show ip interface brief
show vlan brief
show running-config
```

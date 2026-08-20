# 运行所需 Secrets 配置清单

| Secret 名称 | 来源文件 | 描述说明 | 格式详细描述 |
| :--- | :--- | :--- | :--- |
| `NX_CLIENT_CERT_PEM_B64` | `certificat.pem` | 任天堂 CDN 通信所需的客户端 mTLS 证书 | 标准 PEM 格式证书文本（包含 `-----BEGIN CERTIFICATE-----` 至 `-----END CERTIFICATE-----`）经 Base64 编码后的字符串 |
| `NX_CLIENT_KEY_PEM_B64` | `certificat.pem` | 任天堂 CDN 通信所需的客户端私钥 | 标准 PEM 格式私钥文本（包含 `-----BEGIN RSA PRIVATE KEY-----` 或 `-----BEGIN PRIVATE KEY-----`）经 Base64 编码后的字符串 |
| `NX_DEVICE_ID` | `PRODINFO.bin` | 机器专属设备标识符（Device ID） | 恰好 16 位的十六进制明文字符串（正则匹配 `^[0-9A-Fa-f]{16}$`，例如 `0123456789abcdef`），直接填入无需 Base64 编码 |
| `NX_HACTOOL_KEYS_B64` | `prod.keys` | `hactool` 解析 CNMT 所需的最小密钥集 | 纯文本键值对格式（每行 `name = hex_value`，必须包含 64 位 Hex 的 `header_key` 以及 32 位 Hex 的 `key_area_key_application_*`、`key_area_key_ocean_*`、`key_area_key_system_*`）经 Base64 编码后的字符串 |

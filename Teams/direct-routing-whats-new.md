---
title: 新的直接路由功能
ms.reviewer: CarolynRowe
author: wlibebe
ms.author: wlibebe
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 本文將說明直接路由的新增功能。 請經常回來查看更新。
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.collection:
- M365-voice
ms.openlocfilehash: 87befd2ff63fc5e3f0aa9e1c715972e5061b8fc7
ms.sourcegitcommit: e09591a0df9848b50bfeda29650e91e9d35724af
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/24/2023
ms.locfileid: "69981868"
---
# <a name="whats-new-for-direct-routing"></a>直接路由的新功能

本文將說明直接路由的新增功能。 請經常回來查看更新。

## <a name="new-direct-routing-sip-endpoints"></a>新的直接路由 SIP 端點 

Microsoft 將推出新的訊號 IP 給 Teams 直接路由 SIP 端點。 為確保這項變更不會影響您的服務可用性，請確定您的會話框線控制器和防火牆已設定為使用分類和 ACL 規則的建議子網 52.112.0.0/14 和 52.120.0.0/14。 如需詳細資訊，請參閱[Microsoft 365、Office 365 和 Office 365 GCC 環境](direct-routing-plan.md#microsoft-365-office-365-and-office-365-gcc-environments)。  

## <a name="trunk-demoting-logic-based-on-sip-options"></a>以 SIP 選項為基礎的主幹降級邏輯

系統會針對主幹健康情況引進以 SIP 選項為基礎的新功能。 在閘道組態中啟用 (請參閱Set-CsOnlinePSTNGateway Cmdlet 和 SendSipOptions 參數) ，撥出電話的路由邏輯會降級未定期傳送 SIP 選項 (預期期間的主幹是 SBC 每分鐘傳送一個 SIP 選項) 到 Microsoft 後端。 這些降級的樹幹會放在待發通話可用的主幹清單結尾，並嘗試做為最後一個;以降低通話設定時間。
針對該功能啟用的任何主幹，在五分鐘內不會傳送至少一個 SIP 選項給任何 Microsoft 地區 (NOAM、EMEA、APAC、OCEA) SIP Proxy 會被視為降級。 如果主幹只將 SIP 選項傳送到 Microsoft 地區 SIP Proxy 的子集，則會先嘗試這些路由，其餘路由會降級。


## <a name="sip-support"></a>SIP 支援

Microsoft 將于 2022 年 6 月 1 日從直接路由設定中移除對 sip-all.pstnhub.microsoft.com 和 sip-all.pstnhub.gov.teams.microsoft.us FQDN 的支援。

如果在 6 月 1 日之前未採取任何動作，使用者將無法透過直接路由撥打或接聽電話。

若要防止服務影響：

- 針對任何分類或 ACL 規則，請使用建議的子網： (52.112.0.0/14 和 52.122.0.0/15) 。
- 在設定直接路由的會話框線控制項時，停止使用 sip-all FQDN。

如需詳細資訊，請參閱 [規劃直接路由](direct-routing-plan.md)。

## <a name="tls-certificates"></a>TLS 憑證

Microsoft 365 正在更新 Teams 和其他服務，以使用另一組跟憑證授權單位單位 (CAs) 。

如需詳細資訊和受影響服務的完整清單，請參閱 [包括 Microsoft Teams 在內的 Microsoft 365 服務的 TLS 憑證變更](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/tls-certificate-changes-to-microsoft-365-services-including/ba-p/3249676)。

## <a name="certificate-authorities"></a>憑證授權單位單位

自 2022 年 2 月 1 日起，直接路由 SIP 介面只會信任由憑證授權單位單位 (CAs 簽署的憑證，) 屬於 Microsoft 信任的根憑證計畫。 請採取下列步驟以避免服務影響：

- 確定您的 SBC 憑證是由屬於 Microsoft 信任根憑證計畫一部分的 CA 簽署。
- 確認憑證的延伸金鑰使用 (EKU) 副檔名包含「伺服器驗證」。

如需 Microsoft 信任根憑證計畫的詳細資訊，請參閱 [計畫需求 - Microsoft Trusted Root Program](/security/trusted-root/program-requirements)。

如需信任的 CA 清單，請參閱 [Microsoft 隨附的 CA 憑證清單](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)。

## <a name="replace-headers"></a>取代標頭

自 2022 年 4 月開始，直接路由會拒絕已定義 [取代標頭] 的 SIP 要求。 Microsoft 將 Replaces 標頭傳送到會話框線控制器 (SBC) 的流量不會有任何變更。

檢查您的 SBC 設定，並確定您沒有在 SIP 要求中使用 [取代標頭]。

## <a name="tls10-and-11"></a>TLS1.0 和 1.1

為了提供一流的加密給我們的客戶，Microsoft 計畫將傳輸層安全性 (TLS) 版本 1.0 和 1.1 停用。 Microsoft 將于 2022 年 4 月 3 日強制使用 TLS1.2 直接路由 SIP 介面。

若要避免任何服務影響，請確定您的 SBC 已設定為支援 TLS1.2，而且可以使用下列其中一個密碼套件連線：

- TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384，也即 ECDHE-RSA-AES256-GCM-SHA384
- TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256，也即 ECDHE-RSA-AES128-GCM-SHA256
- TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384，也即 ECDHE-RSA-AES256-SHA384
- TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256，也即 ECDHE-RSA-AES128-SHA256

## <a name="related-topics"></a>相關主題

- [直接路由 - SIP 通訊協定](direct-routing-protocols-sip.md)

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
ms.openlocfilehash: 8db0f0c4d29f786166098587aafc3ec1db256e38
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271458"
---
# <a name="whats-new-for-direct-routing"></a>直接路由的新功能

本文將說明直接路由的新增功能。 請經常回來查看更新。

## <a name="sip-support"></a>SIP 支援

Microsoft 將于 2022 年 6 月 1 日從直接路由設定中移除對 sip-all.pstnhub.microsoft.com 和 sip-all.pstnhub.gov.teams.microsoft.us FQDN 的支援。

如果在 6 月 1 日之前未採取任何動作，使用者將無法透過直接路由撥打或接聽電話。

若要防止服務影響：

- 針對任何分類或 ACL 規則，請使用建議的子網： (52.112.0.0/14 和 52.120.0.0/14) 。
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

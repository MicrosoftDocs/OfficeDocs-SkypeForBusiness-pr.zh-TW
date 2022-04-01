---
title: 新增直接路由
ms.reviewer: CarolynRowe
author: wlibebe
ms.author: wlibebe
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 本文將說明直接路由的新增功能。 經常回來查看更新。
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 53a1c2730ebf6db06fb92ac2fc4e0873563c98ce
ms.sourcegitcommit: 9e868a155bcd20dd5dafdedcff091ff77ca7398b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/31/2022
ms.locfileid: "64584327"
---
# <a name="whats-new-for-direct-routing"></a>直接路由的新增功能

本文將說明直接路由的新增功能。 經常回來查看更新。

## <a name="sip-support"></a>SIP 支援

Microsoft 將于 2022 年 6 月 1 日從直接路由 sip-all.pstnhub.microsoft.com 移除 sip-all.pstnhub.gov.teams.microsoft.us FQNS 的支援。

如果在 6 月 1 日之前未採取任何動作，使用者將無法透過直接路由撥打或接聽電話。

若要避免服務影響：

- 使用建議子網： (52.112.0.0/14 和 52.120.0.0/14) 以用於任何分類或 ACL 規則。
- 在針對直接路由進行會話邊界控制項時，停止使用 sip-all FQDN。

詳細資訊，請參閱規劃 [直接路由](direct-routing-plan.md)。

## <a name="tls-certificates"></a>TLS 憑證

Microsoft 365更新 Teams服務，以使用一組不同的根憑證授權單位 (CA) 。

若要瞭解詳細資訊及受影響服務的完整清單，請參閱 TLS 憑證變更至 Microsoft 365[服務，](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/tls-certificate-changes-to-microsoft-365-services-including/ba-p/3249676)Microsoft Teams。

## <a name="certificate-authorities"></a>憑證頒發機構

從 2022 年 2 月 1 日起，直接路由 SIP 介面只會信任由憑證授權單位 (CA) 所簽署的憑證，這些憑證屬於 Microsoft 信任的根憑證計畫。 請採取下列步驟以避免服務影響：

- 請確定您的 SBC 憑證是由 Microsoft 信任的根憑證計畫一部分的 CA 簽署。
- 確認 EKU 的擴充金鑰使用量 (憑證) 副檔名包含「伺服器驗證」。

有關 Microsoft 根信任證書計畫的資訊，請參閱計畫 [需求 - Microsoft 信任的根程式](/security/trusted-root/program-requirements)。

有關信任的 CA 清單，請參閱 [Microsoft 包含 CA 憑證清單](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)。

## <a name="replace-headers"></a>取代頁標題

從 2022 年 4 月開始，直接路由會拒絕已定義取代標題的 SIP 要求。 Microsoft 在 SBC 中傳送取代頁眉至會話邊界控制器的資料流程 (變更) 。

檢查您的 SBC 配置，確定您不是在 SIP 要求中使用取代頁標題。

## <a name="tls10-and-11"></a>TLS1.0 和 1.1

為了為客戶提供一流的加密功能，Microsoft 計畫將傳輸層安全性 (TLS) 版本 1.0 和 1.1 取消。 Microsoft 將于 2022 年 4 月 3 日強制 TLS1.2 使用直接路由 SIP 介面。

若要避免任何服務影響，請確保您的 SBCs 已配置為支援 TLS1.2，並可以使用下列其中一個密碼套件進行連結：

- TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384例如 ECDHE-RSA-AES256-GCM-SHA384
- TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256例如 ECDHE-RSA-AES128-GCM-SHA256
- TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384例如 ECDHE-RSA-AES256-SHA384
- TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256例如 ECDHE-RSA-AES128-SHA256

## <a name="related-topics"></a>相關主題

- [直接路由 - SIP 通訊協定](direct-routing-protocols-sip.md)

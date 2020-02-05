---
title: 更新邊緣憑證
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: 本附錄包含 microsoft Teams 和商務用 Skype 雲端合併彙算的過程中更新邊緣憑證的詳細的步驟。
ms.openlocfilehash: c4339eec5fa303429fdf8f42a7273c8f20f94e5b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762851"
---
# <a name="update-the-edge-certificate"></a>更新邊緣憑證

更新邊緣憑證是重要步驟，確保 SipDomain1 與內部部署環境可以加入 SipDomain2 的雲端環境，並確保跨兩個 SIP 網域共用的位址空間環境中適當路由。 請參閱中的步驟 14[雲端彙總針對小組與商務用 Skype](cloud-consolidation.md)內容中，您可能會執行此步驟。 在我們的範例，SipDomain1 是 AcquiredCompany。<span>com 和 SipDomain2 是 OriginalCompany。<span>com。

必須更新內部部署環境中的所有 edge server 上的憑證的主體替代名稱 (SAN)，以包括單純的線上租用戶中存在的所有 SIP 網域 (不含任何 onmicrosoft。<span>com 網域），格式為 「 sip。\<網域> 」。  在我們的範例，這是 sip。OriginalCompany。<span>com。 此步驟是關鍵移轉至雲端的任何使用者之前執行。

**步驟：**

1.  取得新的外部邊緣憑證邊緣具有雲端環境中的所有 SIP 網域在 SAN 中的所有現有項目加上額外的項目 (不含 *。 onmicrosoft.com 網域) 中的表單 」 sip。<DomainName>"。
2.  將憑證安裝在本機上每部 edge server，並將其指派給每個 edge service 的 Skype Edge 服務。  如需詳細步驟，請參閱[在商務用 Skype Server 2015 中部署 Edge Service](https://technet.microsoft.com/library/dn951368.aspx)中的 「 外部 Edge 介面的憑證 」 一節。
3.  重新啟動每一部 edge server 上的 [Edge service。 您可以針對單一] 方塊中，使用下列 PowerShell 命令來這麼做：

    ```PowerShell
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a>另請參閱

[針對小組與 Skype for Business 的雲端彙總](cloud-consolidation.md)

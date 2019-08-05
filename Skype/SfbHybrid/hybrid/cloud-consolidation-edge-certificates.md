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
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: 此附錄包含更新 edge 憑證的詳細步驟, 做為小組和商務用 Skype 的雲端合併的一部分。
ms.openlocfilehash: 1c3aaa8859db530ceccbebc68ae76f21e8d4a77f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36185500"
---
# <a name="update-the-edge-certificate"></a>更新邊緣憑證

更新 edge 憑證是主要步驟, 可確保 SipDomain1 的內部部署環境可以使用 SipDomain2 加入雲端環境, 並確保透過兩個 SIP 網域在共用位址空間環境中正確路由。 請參閱適用于[團隊與商務用 Skype 之雲端整合](cloud-consolidation.md)中的步驟 14, 以取得您可能會執行此步驟的內容。 在我們的範例中, SipDomain1 是 AcquiredCompany。<span>Com 和 SipDomain2 是 OriginalCompany。<span>com。

在內部部署環境中, 所有邊緣伺服器上的憑證的主體替換名稱 (SAN) 都必須更新, 才能包含純粹線上租使用者中存在的所有 SIP 網域 (不包括任何 onmicrosoft<span> )。com 網域), 其形式為「sip。\<網域> "。  在我們的範例中, 這是 sip。OriginalCompany.<span>com。 在將任何使用者移植到雲端之前, 必須先執行此步驟。

**步驟**

1.  針對雲端環境中的所有 SIP 網域 (不包括 *. onmicrosoft.com domain), 以「sip」形式取得所有現有專案的邊緣的新外部邊緣憑證, 以及 SAN 中所有 SIP 網域的 SAN 中的其他專案。<DomainName>"。
2.  在每個 edge 伺服器上本機安裝證書, 並將它指派給每個 edge 服務上的 Skype Edge 服務。  如需詳細步驟, 請參閱[商務用 Skype Server 2015 的部署邊緣服務](https://technet.microsoft.com/en-us/library/dn951368.aspx)中的「外部邊緣介面憑證」一節。
3.  在每個邊緣伺服器上重新開機 Edge 服務。 您可以針對單一方塊執行下列 PowerShell 命令:

    ```
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a>另請參閱

[團隊與商務用 Skype 的雲端整合](cloud-consolidation.md)
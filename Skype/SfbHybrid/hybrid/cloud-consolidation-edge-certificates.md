---
title: 更新 Microsoft Edge 憑證
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
description: 本附錄包含更新 edge 憑證以供小組和商務用 Skype 進行雲端合併的詳細步驟。
ms.openlocfilehash: 724ac63239c881283368fbd617ce0654d49fc0e6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120342"
---
# <a name="update-the-edge-certificate"></a>更新 Microsoft Edge 憑證

更新 edge 憑證是重要步驟，可確保具有 SipDomain1 的部署環境可以加入雲端環境與 SipDomain2，並確保在共用位址空間環境中正確地路由傳送到兩個 SIP 網域。 如需執行此步驟的內容，請參閱 [Cloud 整合中針對團隊和商務用 Skype](cloud-consolidation.md) 的步驟14。 在我們的範例中，SipDomain1 是 AcquiredCompany。 <span>com 和 SipDomain2 為 OriginalCompany。 <span>Com。

在內部部署環境中，所有 edge server 上的主體替代名稱 (的憑證) 必須更新，以包含存在於純線上承租人中的所有 SIP 網域 (排除任何 name.onmicrosoft.com17。 <span>com 網域) ，格式為 "sip \<domain> "。  在我們的範例中，這是 sip。OriginalCompany。 <span>Com。 在將任何使用者遷移至雲端之前，這是非常重要的步驟。

**步驟：**

1.  針對雲端環境中的所有 SIP 網域，取得現有的現有專案和 SAN 中的其他專案的新外部 Edge 憑證 (包含) "SIP" 的 onmicrosoft.com 網域 <DomainName> 。
2.  在每一部 edge server 上以本機方式安裝憑證，並將它指派給每個 edge service 上的 Skype Edge service。  如需詳細步驟，請參閱 [Deploy Edge Service In 商務用 Skype Server 2015](../../SfbServer/deploy/deploy-edge-server/deploy-edge-servers.md)中的「外部 Edge interface 憑證」一節。
3.  在每一部 Edge server 上重新開機 Edge service。 您可以使用下列 PowerShell 命令，在單一方塊中執行這項操作：

    ```PowerShell
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a>另請參閱

[小組和商務用 Skype 的雲端整合](cloud-consolidation.md)
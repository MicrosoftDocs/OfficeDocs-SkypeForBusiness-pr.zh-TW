---
title: 在解除委任內部部署環境時管理 DNS 專案
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: 如何在解除委任內部部署商務用 Skype環境時管理 DNS 專案的指示。
ms.openlocfilehash: c21a736c19ecec41ddc0458931675ca8ede34ed2
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671879"
---
# <a name="update-dns-entries-to-enable-your-organization-to-be-all-teams-only"></a>更新 DNS 專案，讓您的組織只Teams

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

先前有內部部署 商務用 Skype Server 或 Lync Server 的組織，可能仍有指向內部部署商務用 Skype部署的 DNS 專案。 如果您的組織包含內部部署商務用 Skype使用者，則需要這些記錄。 不過，一旦您的組織不再有任何內部部署商務用 Skype或 Lync Server 使用者，內部部署就不再需要這些原始記錄，而且 **這些 DNS 專案必須更新為指向Microsoft 365 (或在某些情況下移除)** 當您從內部部署移轉至僅限Teams。 *Microsoft 無法代表您更新這些 DNS 記錄。*

嘗試將 TeamsOnly 授與整個租使用者時，Teams會檢查 DNS，以判斷下列任何 DNS 記錄是否存在於您組織中每個Microsoft 365驗證的網域中。 如果找到任何記錄，而且它們指向Microsoft 365以外的專案，則嘗試將租使用者共存模式變更為 TeamsOnly 會在設計上失敗。 這可防止內部部署使用者的混合式組織誤將 TeamsOnly 模式套用至租使用者，因為這樣做會中斷組織中所有內部部署商務用 Skype使用者的同盟， (使用Teams或商務用 Skype) 。

## <a name="how-to-identify-stale-dns-records"></a>如何識別過時的 DNS 記錄

若要識別任何無法讓組織變成所有Teams的 DNS 記錄，您可以使用 Teams 系統管理中心將共存模式變更為 TeamsOnly。 移至 **Teams**  >  **Teams升級設定**。 任何防止組織變成Teams的 DNS 記錄都會包含在錯誤訊息中。  如果找不到 DNS 記錄，您組織的共存模式將會變更為 TeamsOnly。

或者，您可以使用 Teams PowerShell 來執行相同的動作，如下所示：

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Global
   ```

## <a name="dns-records-to-be-updated"></a>要更新的 DNS 記錄

如果您的組織不再有任何使用者裝載于內部部署商務用 Skype Server或 Lync Server，您必須執行下列動作：

- 更新下商務用 Skype DNS 記錄清單，以指向Microsoft 365 (，而不是內部部署) 。 如果您有一個以上的 SIP 網域，則必須針對每個為Microsoft 365驗證網域的 SIP 網域執行此動作。

- 如果不再使用 SIP 網域，請移除商務用 Skype DNS 記錄。

在您找到下列任何記錄的每個網域中，更新它們，如下所示：

|Record type (記錄類型)|名稱|TTL|Priority (優先順序)|Weight (權數)|Port (連接埠)|Value (值)|
|---|---|---|---|---|---|---|
|SRV|_sipfederationtls._tcp|3600|100|1|5061|sipfed.online.lync.com|
|SRV|_sip._tls|3600|100|1|443|sipdir.online.lync.com|
|CNAME|lyncdiscover|3600|不適用|不適用|不適用|webdir.online.lync.com|
|CNAME|sip|3600|不適用|不適用|不適用|sipdir.online.lync.com|

此外，如果) 可以刪除，則會 (符合或對話方塊的 CNAME 記錄。 最後，應該移除內部網路中商務用 Skype的任何 DNS 記錄。

> [!NOTE]
> 在極少數情況下，將 DNS 從指向內部部署變更為您組織的Microsoft 365，可能會導致與其他組織同盟停止運作，直到其他組織更新其同盟設定為止：
>
> - 任何使用舊版直接同盟模型 (也稱為 Allowed Partner Server) 的同盟組織，都必須更新其允許的網域專案，讓其組織移除 Proxy FQDN。 此舊版同盟模型不是以 DNS SRV 記錄為基礎，因此，一旦您的組織移至雲端，這類設定將會過時。
>
> - 沒有已啟用 sipfed.online.lync 主機提供者的任何同盟組織。 <span>com 必須更新其組態，才能啟用此功能。 只有在同盟組織純粹是內部部署且從未與任何混合式或線上租使用者同盟時，才可能發生這種情況。 在這種情況下，除非這些組織啟用其主機提供者，否則與這些組織的同盟將無法運作。
>
> 如果您懷疑任何同盟合作夥伴可能正在使用直接同盟，或尚未與任何線上或混合式組織同盟，建議您在準備完成雲端移轉時傳送相關通訊給他們。

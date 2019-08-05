---
title: 停用混合式完成到雲端的遷移
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
description: 此附錄包含停用混合式的詳細步驟, 做為小組和商務用 Skype 的雲端整合的一部分。
ms.openlocfilehash: 805010aa16ca8159b5e274847ca7ca2b296f214d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36185503"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a>停用混合式完成到雲端的遷移

將所有使用者從內部部署移至雲端之後, 您就可以停止使用內部部署商務用 Skype 部署。 除了移除任何硬體之外, 重要的步驟是透過停用混合式, 以邏輯方式將該內部部署與 Office 365 分開。 停用混合式包括3個步驟:

1. 更新 DNS 記錄以指向 Office 365。
2. 停用 Office 365 租使用者中的分割網域。
3. 停用內部部署中的功能, 以與 Office 365 進行通訊。


這些步驟應一起做為一個單元。 以下提供詳細資料。

> [!Note] 
> 在少數情況下, 將 DNS 從指向您組織的 Office 365 的內部部署變更為其他組織, 可能會造成與其他組織的同盟停止運作, 直到其他組織更新其同盟設定為止:<ul><li>
任何使用舊版直接聯盟模型 (又稱為 [允許的夥伴伺服器]) 的同盟組織, 都必須更新其組織的允許網域專案, 才能移除 proxy FQDN。 此舊版同盟模型不是以 DNS SRV 記錄為基礎, 因此當您的組織移到雲端之後, 這類設定就會過期。 </li><li>沒有已啟用 sipfed 的主機服務提供者的任何聯盟組織。 lync。<span>com 將需要更新其設定, 才能啟用。 只有在同盟組織純粹在內部部署且從未與任何混合式或線上租使用者進行同盟時, 才能使用這種情況。 在這種情況下, 與這些組織的同盟在啟用其主機提供者之前將無法運作。</li></ul>如果您懷疑任何聯盟夥伴都可能使用直接聯盟, 或是與任何線上或混合式組織共同作業, 我們建議您在準備完成您的雲端遷移時, 傳送與此相關的通訊。

1.  *更新 DNS 以指向 Office 365。*
組織內部部署組織的外部 DNS 必須更新, 才能讓商務用 Skype 記錄指向 Office 365, 而不是內部部署的部署。 說

    |記錄類型|名稱|TTL|值|
    |---|---|---|---|
    |DNS-SRV|_sipfederationtls._tcp|3600|100 1 5061 sipfed (線上) lync。<span>com|
    |DNS-SRV|_sip._tls|3600|100 1 443 sipdir (線上) lync。<span>com|
    |CNAME| lyncdiscover|   3600|   webdir 為 admin. lync。<span>com|
    |CNAME| 呼吸|    3600|   sipdir. lync。<span>com|
    |CNAME| 符合|   3600|   webdir 為 admin. lync。<span>com|
    |CNAME| 撥  |3600|  webdir 為 admin. lync。<span>com|

2.  *停用 Office 365 租使用者共用的 SIP 位址空間。*
下列命令必須從商務用 Skype Online PowerShell 視窗中完成。

    `Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false`
 
3.  *停用內部部署中的功能, 以與 Office 365 進行通訊。*  
下列命令必須從內部部署的 PowerShell 視窗完成。  如果您先前已匯入商務用 Skype Online 會話, 請開始新的商務用 Skype PowerShell 會話。

    `Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false`

## <a name="see-also"></a>另請參閱

[團隊與商務用 Skype 的雲端整合](cloud-consolidation.md)
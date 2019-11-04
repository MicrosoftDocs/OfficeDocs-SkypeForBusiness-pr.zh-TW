---
title: 停用來完成遷移至雲端混合式
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
description: 本附錄包含詳細的步驟，停用混合式雲端合併彙算 Teams 和商務用 Skype 的一部分。
ms.openlocfilehash: f78c5a5cb792ecdb39125292c531097219dc58e3
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/01/2019
ms.locfileid: "37924964"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a>停用來完成遷移至雲端混合式

您已經移動所有使用者從內部部署到雲端後，您可以解除委任商業部署內部部署商務用 Skype。 除了移除任何硬體，是以邏輯方式分隔從 Office 365 的內部部署停用混合式的重要步驟。 停用混合式所組成的 3 個步驟：

1. 更新為指向 Office 365 的 DNS 記錄。
2. 停用 Office 365 租用戶中的分割網域。
3. 停用通訊與 Office 365 中內部部署的能力。


您可以視為一個單位一起完成這些步驟。 詳細資料如下所示。 此外，管理的指導方針的電話號碼移轉的使用者，一旦中斷連接內部部署。

> [!Note] 
> 在極罕見的情況下，變更 DNS 從指向內部部署 Office 365 為您的組織可能會導致同盟與停止運作直到其他組織更新其同盟設定某些其他組織：<ul><li>
任何使用較舊的直接同盟模式 （也稱為允許協力程式伺服器） 的同盟的組織需要更新為其組織若要移除之 proxy FQDN 其允許的網域項目。 此舊版同盟模型不基礎 DNS SRV 記錄，因此這類設定將會過時，一旦您的組織移至雲端。 </li><li>任何不需要 sipfed.online.lync 啟用主機服務提供者的同盟的組織。<span>，需要更新其組態，以便讓，com。 如果同盟的組織是純內部部署和永遠不會有任何混合或線上租用戶與同盟，這種情況下才可以。 在這種情況下，與這些組織建立同盟將無法運作之前他們啟用其主機服務提供者。</li></ul>如果您懷疑同盟協力任何的廠商可能會使用直接同盟或與任何有 online 同盟或混合組織中，我們建議您傳送這些有關此通訊，準備完成移轉至雲端。

1.  *更新 DNS 以指向 Office 365。*
在內部部署組織的組織的外部 DNS 必須進行更新，讓 Skype for Business 記錄指向 Office 365 而不是在內部部署。 特別是：

    |Record type (記錄類型)|名稱|TTL|Value (值)|
    |---|---|---|---|
    |SRV|_sipfederationtls._tcp|3600|100 1 5061 sipfed.online.lync。<span>com|
    |SRV|_sip._tls|3600|100 1 443 sipdir.online.lync。<span>com|
    |CNAME| lyncdiscover|   3600|   webdir.online.lync。<span>com|
    |CNAME| sip|    3600|   sipdir.online.lync。<span>com|
    |CNAME| 符合|   3600|   webdir.online.lync。<span>com|
    |CNAME| dialin  |3600|  webdir.online.lync。<span>com|

2.  *停用 Office 365 租用戶中的共用的 SIP 位址空間。*
下列命令，需要完成從 Skype for Business Online PowerShell 視窗。

    `Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false`
 
3.  *停用通訊與 Office 365 中內部部署的能力。*  
必須從內部部署的 PowerShell] 視窗中執行以下命令。  如果您有先前匯入 Skype for Business Online 工作階段啟動新的 Skype for Business PowerShell 工作階段。

    `Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false`

### <a name="managing-phone-numbers-for-users-who-were-migrated-from-on-premises"></a>管理已從內部部署移轉的使用者的電話號碼

系統管理員可以管理先前從內部部署 Skype for Business Server 至雲端，即使之後移動解除委任內部部署的使用者。 有 2 不同的可能性：
1.  如果使用者有 lineURI 內部部署進行移動之前 (可能因為使用者已啟用 Enterprise voice)，如果您想要變更 lineURI，您必須執行此動作的內部部署 AD，並讓值流程至 AAD。 這不需要內部 Skype for Business Server。 相反地，此屬性，可以編輯 Msrtcsip-line，直接在內部部署 Active Directory 中，使用 Active Directory 使用者及電腦] MMC 嵌入式管理單元中，或透過 PowerShell。 如果使用 MMC 嵌入式管理單元，請開啟 [屬性] 頁面上的使用者，按一下 [屬性編輯器] 索引標籤並尋找 Msrtcsip-line。

2.  如果使用者沒有 lineURI 在內部進行移動之前的值，您可以修改 skype 組 get-csuser cmdlet 中使用-onpremLineUri 參數 for Business Online Powershell 模組 LineURI。

## <a name="see-also"></a>另請參閱

[針對小組與 Skype for Business 的雲端彙總](cloud-consolidation.md)

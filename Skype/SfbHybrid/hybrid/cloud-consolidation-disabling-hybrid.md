---
title: 停用混合式以完成移轉至雲端
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
description: 本附錄包含針對團隊和商務用 Skype 進行雲合併時，停用混合的詳細步驟。
ms.openlocfilehash: 039e8a30495567fe818fe4d60b863f37cf94e049
ms.sourcegitcommit: 0835f4335ebc8ca53b8348e0b1b906828eb4e13e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/28/2020
ms.locfileid: "43918732"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a>停用混合式以完成移轉至雲端

將所有使用者從內部部署移至雲端之後，您就可以解除內部部署的商務用 Skype。 除了移除任何硬體以外，重要的步驟是透過停用混合式的方式，在邏輯上將該內部部署與 Office 365 分開。 停用混合式包含三個步驟：

1. 更新 DNS 記錄，使它指向 Office 365。

2. 停用 Office 365 組織中的分割網域。

3. 停用內部部署中與 Office 365 通訊的功能。

這些步驟應該一起做為一個單位。 以下提供詳細資料。 此外，在中斷內部部署的部署後，也會提供指導方針來管理遷移使用者的電話號碼。

> [!Note] 
> 在極少的情況下，將組織的內部部署至 Office 365 的 DNS 變更為您的組織可能會造成其他一些組織的同盟停止運作，直到其他組織更新其同盟設定為止：<ul><li>
任何使用舊版直接同盟模型（也稱為「允許夥伴伺服器」）的同盟組織，都必須更新其組織的允許網域專案，以移除 proxy FQDN。 這種舊版同盟模型不是以 DNS SRV 記錄為基礎，因此當您的組織移至雲端時，此設定將會到期。 </li><li>任何沒有啟用 sipfed 之主機服務提供者的同盟組織。<span>com 必須更新其設定，才能啟用該功能。 只有在同盟組織完全存在於內部部署，且決不會與任何混合式或線上租使用者同盟的情況下，才可能出現這種情況。 在此情況下，與這些組織的同盟必須啟用其主機服務提供者後，才能運作。</li></ul>如果您懷疑任何同盟協力廠商可能使用的是直接同盟或尚未與任何線上或混合組織同盟，我們建議您在準備完成對雲端的遷移時，向他們傳送此資訊的通訊。

1.  *將 DNS 更新為指向 Office 365。*
組織的外部 DNS 必須更新內部部署組織，以便商務用 Skype 記錄指向 Office 365，而不是內部部署。 特別是：

    |Record type (記錄類型)|名稱|TTL|Value (值)|
    |---|---|---|---|
    |SRV|_sipfederationtls。 _tcp|3600|100 1 5061 sipfed （lync）。<span>com|
    |SRV|_sip。 _tls|3600|100 1 443 sipdir （lync）。<span>com|
    |CNAME| lyncdiscover|   3600|   webdir。<span>com|
    |CNAME| sip|    3600|   sipdir。<span>com|
    |CNAME| 滿足|   3600|   webdir。<span>com|
    |CNAME| 入  |3600|  webdir。<span>com|

2.  *停用 Office 365 組織中的共用 SIP 位址空間。*
以下的命令必須透過商務用 Skype Online PowerShell 視窗執行。

    ```PowerShell
    Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
    ```
 
3.  *停用內部部署中與 Office 365 通訊的功能。*  
以下是必須從內部部署 PowerShell 視窗執行的命令：

    ```PowerShell
    Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
    ```

### <a name="manage-phone-numbers-for-users-who-were-migrated-from-on-premises"></a>管理從內部部署遷移之使用者的電話號碼

管理員可以管理先前已從內部部署商務用 Skype Server 移至雲端的使用者，即使已解除內部部署的部署。 有兩種不同的可能性：

- 在移動之前，使用者沒有 LineURI 內部部署的值。 

  在此情況下，您可以在商務用 Skype Online PowerShell 模組中，使用[Set-CsUser Cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps)中的-onpremLineUri 參數修改 LineURI。

- 使用者在移動之前有 LineURI 內部部署（原因是使用者已啟用 Enterprise Voice）。 

  如果您想要變更 LineURI，您必須在內部部署 Active Directory 中執行這項作業，並讓此值流向 Azure AD。 這不需要內部部署商務用 Skype Server。 相反地，您可以使用 Active Directory 使用者和電腦 MMC 嵌入式管理單元，或是使用 PowerShell，直接在內部部署 Active Directory 中編輯此屬性 msRTCSIP 行。 如果您使用的是 MMC 嵌入式管理單元，請開啟至使用者的 [內容] 頁面，按一下 [屬性編輯器] 索引標籤，然後尋找 msRTCSIP 行。

  ![Active Directory 使用者和電腦工具](../media/disable-hybrid-1.png)

## <a name="see-also"></a>另請參閱

[小組和商務用 Skype 的雲端整合](cloud-consolidation.md)

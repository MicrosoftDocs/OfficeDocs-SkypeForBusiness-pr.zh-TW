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
ms.openlocfilehash: 93aad1ea230d9edbb81673a3ddabc7088b06d422
ms.sourcegitcommit: a28232f16bfefe6414d1f5a54d5f8c8665eb0e23
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277260"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a>停用混合式以完成移轉至雲端

將所有使用者從內部部署移至雲端之後，您就可以解除內部部署的商務用 Skype。 除了移除任何硬體之外，重要的步驟是透過停用混合式，以邏輯方式將該內部部署與 Microsoft 365 或 Office 365 分開。 停用混合式包含三個步驟：

1. 更新 DNS 記錄，以指向 Microsoft 365 或 Office 365。

2. 停用 Microsoft 365 或 Office 365 組織中的分割網域。

3. 停用內部部署中與 Microsoft 365 或 Office 365 通訊的功能。

這些步驟應該一起做為一個單位。 以下提供詳細資料。 此外，在中斷內部部署的部署後，也會提供指導方針來管理遷移使用者的電話號碼。

完成這些步驟之後，就不再使用內部部署商務用 Skype 伺服器，而且可以重新映射這些伺服器。

> [!Important] 
>您應該繼續讓 Active Directory 同步處理中的 msRTCSIP 屬性，透過 Azure AD 連接至 Azure AD。  除非受到支援，否則請勿清除任何這些屬性。  請勿在內部部署環境中執行 Disable-Get-csuser。 如果您需要修改使用者的 SIP 位址，請在您的內部部署 Active Directory 中執行這項作業，並透過 Azure AD Connect 將此變更同步處理到 Azure AD Connect，如下所述。 同樣地，如果您需要變更電話號碼，且已在內部部署中定義使用者的 LineURI，您應該在內部部署 Active Directory 中修改此值。
>在您從內部部署遷移之後清除內部部署 msRTCSIP 屬性，可能會導致使用者的服務遺失！


1.  *將 DNS 更新為指向 Microsoft 365 或 Office 365。*
組織的外部 DNS 必須更新內部部署組織，以便商務用 Skype 記錄指向 Microsoft 365 或 Office 365，而不是內部部署。 特別是：

    |Record type (記錄類型)|名稱|TTL|Value (值)|
    |---|---|---|---|
    |SRV|_sipfederationtls._tcp|3600|100 1 5061 sipfed （lync <span> ）。Com|
    |SRV|_sip._tls|3600|100 1 443 sipdir （lync <span> ）。Com|
    |CNAME| lyncdiscover|   3600|   <span>webdir。Com|
    |CNAME| sip|    3600|   <span>sipdir。Com|
    |CNAME| 滿足|   3600|   <span>webdir。Com|
    |CNAME| 入  |3600|  <span>webdir。Com|

    此外，如果存在) 可刪除，則為符合或撥入 (的 CNAME 記錄。 最後，您應該移除內部網路中商務用 Skype 的任何 DNS 記錄。

    > [!Note] 
    > 在極少的情況下，將組織的內部部署至 Office 365 的 DNS 變更為您的組織可能會造成其他一些組織的同盟停止運作，直到其他組織更新其同盟設定為止：
    >
    > - 任何使用舊版直接同盟模型的同盟組織 (又稱為允許的夥伴伺服器) ，都必須更新其組織的允許網域專案，以移除 proxy FQDN。 這種舊版同盟模型不是以 DNS SRV 記錄為基礎，因此當您的組織移至雲端時，此設定將會到期。
    > 
    > - 任何沒有啟用 sipfed <span> 之主機服務提供者的同盟組織。com 必須更新其設定，才能啟用該功能。 只有在同盟組織完全存在於內部部署，且決不會與任何混合式或線上租使用者同盟的情況下，才可能出現這種情況。 在此情況下，與這些組織的同盟必須啟用其主機服務提供者後，才能運作。
    >
    > 如果您懷疑任何同盟協力廠商可能使用的是直接同盟或尚未與任何線上或混合組織同盟，我們建議您在準備完成對雲端的遷移時，向他們傳送此資訊的通訊。


2.  *停用 Microsoft 365 或 Office 365 組織中的共用 SIP 位址空間。*
以下的命令必須透過商務用 Skype Online PowerShell 視窗執行。

    ```PowerShell
    Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
    ```
 
3.  *停用內部部署中與 Microsoft 365 或 Office 365 通訊的功能。*  
以下是必須從內部部署 PowerShell 視窗執行的命令：

    ```PowerShell
    Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
    ```

### <a name="manage-sip-addresses-and-phone-numbers-for-users-who-were-migrated-from-on-premises"></a>管理從內部部署遷移之使用者的 sip 位址和電話號碼

管理員可以管理先前已從內部部署商務用 Skype Server 移至雲端的使用者，即使已解除內部部署的部署。 如果您想要變更使用者的 SIP 位址或使用者的列 URI (，且已在內部部署 Active Directory) 中定義 SIP 位址或線路 URI，您必須在內部部署 Active Directory 中進行此項操作，並且讓值 (s) 流向 Azure AD。 這不需要內部部署商務用 Skype Server。 相反地，您可以使用 Active Directory 使用者和電腦 MMC 嵌入式管理單元，或是使用 PowerShell，直接在內部部署 Active Directory 中修改這些屬性。 如果您使用的是 MMC 嵌入式管理單元，請開啟使用者的 [屬性] 頁面，按一下 [屬性編輯器] 索引標籤，然後尋找適當的屬性進行修改：

- 若要修改使用者的 SIP 位址，請修改 `msRTCSIP-PrimaryUserAddress` 。 此外，如果 `ProxyAddresses` 屬性包含 sip 值，請更新該 sip 值，使其符合新的值 `msRTCSIP-PrimaryUserAddress` 。 如果不包含 SIP 值，您可以將它保留空白。

- 若要修改使用者的電話號碼，請修改 `msRTCSIP-Line` *是否已有值*。

  ![Active Directory 使用者和電腦工具](../media/disable-hybrid-1.png)
  
如果使用者在 `LineURI` 移動之前沒有內部部署的值，您可以使用商務用 `onpremLineUri` Skype Online PowerShell 模組的 [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) 指令程式中的-參數修改 LineURI。


## <a name="see-also"></a>請參閱

[小組和商務用 Skype 的雲端整合](cloud-consolidation.md)

---
title: 設定 Azure AD 連線
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
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
search.appverid: MET150
description: 設定混合式環境中 Azure AD 連線的指示。
ms.openlocfilehash: cfb290ecc6892001a9e20d9260c54c076a51dfe3
ms.sourcegitcommit: 11a803d569a57410e7e648f53b28df80a53337b6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2021
ms.locfileid: "60887211"
---
# <a name="configure-azure-ad-connect-for-teams-and-skype-for-business"></a>為 Teams 和商務用 Skype 設定 Azure AD Connect

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

 
若要使用 Teams，具有內部部署商務用 Skype Server 或 Lync Server 2013 的組織必須設定 Azure AD 連線，以同步處理內部部署目錄與 Microsoft 365。 具有商務用 Skype Server 內部部署的組織必須確保將正確的 msRTCSIP 屬性同步處理至 Azure AD 中。 在本文中，任何「商務用 Skype Server」參考也適用于 Lync Server 2013。

> [!NOTE]
> - 若要取得完整的功能，也有商務用 Skype 內部部署的現有 Teams 使用者必須將其商務用 Skype 內部部署帳戶移至雲端。 例如，若要取得諸如與商務用 Skype 使用者互動的功能，以及與同盟組織中的使用者進行通訊的功能。 如果內部部署使用者只會使用 Teams，您仍必須將使用者移至雲端，以提供完整 Teams 功能，TeamsOnly 使用者。 若要進行這種遷移，您必須設定 Azure AD 連線，以便啟用混合式。
> - 如果您不打算立即將使用者從內部部署移至雲端，您仍然必須設定 Azure AD 連線，以便 Teams 和商務用 Skype Server 帳戶共同存在。
 

## <a name="background-information"></a>背景資訊

Azure Active Directory 連線保持您的內部部署 Active Directory 持續與 Microsoft 365 進行同步處理。 您的內部部署目錄仍然是授權來源身分識別，而從您的內部部署環境所做的變更會同步處理至 Azure AD。 如需詳細資訊，請參閱 [Azure AD 連線 Sync](/azure/active-directory/hybrid/how-to-connect-sync-whatis)。 您 *組織中的使用者將會在您的內部部署和線上目錄中呈現。*  所有使用 Teams 或商務用 Skype 內部部署的使用者都必須從內部部署同步處理至 Azure AD，以確保這些帳戶的共存。 此外，您也可以借助商務用 Skype 混合式連線（也需要 Azure AD 連線的設定），協助內部部署和線上使用者之間的通訊。


## <a name="configuring-azure-ad-when-you-have-skype-for-business-server"></a>當您有商務用 Skype Server 時設定 Azure AD 

### <a name="general-requirements"></a>一般需求 

若要在內部部署中商務用 Skype Server 與 Teams 共存，來自內部部署部署的某些 Active Directory 屬性必須使用 Azure AD 連線同步處理至 Azure AD 中。 Azure AD 設定連線會自動設定必要的屬性，使其在您的內部部署環境中偵測到商務用 Skype Server 時預設會進行同步處理。 這些屬性包括一般身分識別屬性，例如使用者主體名稱，以及以「msRTCSIP」開頭的屬性，這些屬性是特定于商務伺服器 Skype。 完整的屬性集列于[Azure AD 連線 sync：同步處理至 Azure Active Directory 的屬性](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized#teams-and-skype-for-business-online)。

如果您選擇在 Azure AD 連線中自訂同步處理設定，則必須確定已為 user 物件同步處理下列屬性：
</br>

|屬性|描述|
|---|---|
|msRTCSIP-PrimaryUserAddress| 內部部署環境中的使用者 sip 位址|
|msRTCSIP-DeploymentLocator| 會指出使用者是位於內部部署或雲端|
|msRTCSIP-UserEnabled| 是否已啟用使用者的 SIP 功能|
|||

</br>
</br>
此外，如果您透過內部部署來管理電話系統屬性，您也必須同步處理下列屬性：

|屬性|描述|
|:---|:---|
|msRTCSIP-Line| 使用者的電話號碼|
|msRTCSIP OptionFlags| 會指出是否已啟用使用者的語音功能|
|msRTCSIP OwnerUrn| 用於識別混合應用程式端點|
|||

</br>
Microsoft 建議您同步處理所有包含使用者身分識別的樹系，以及包含商務用 Skype Server 的任何樹系。 如果使用者的身分識別在多個樹系中存在，Azure AD Connect 應執行合併。 只要您遵循本指南，Azure AD Connect 就會自動同步處理正確的屬性，但前提是您沒有修改 Azure AD Connect 中的連接器或同步處理規則。 
  
如果您未同步處理所有包含使用者身分身分識別和商務用 Skype Server 部署的樹系，您必須確保相關的身分識別及商務用 Skype 屬性已正確地填入 Azure AD 中，以供任何使用 Teams 或商務用 Skype 的使用者， (內部部署或線上) 。 這可能需要額外的內部部署目錄同步處理。 如需詳細資訊，請參閱[Azure AD 連線 sync：同步處理至 Azure Active Directory 的屬性](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)。

客戶應負責確保將屬性填入 Azure AD 的適當設定。 請記住下列事項： 

- 使用非標準設定同步處理至 Azure AD 會是危險的。 非標準設定可能會造成線上目錄中的資料損毀。

- 隨著產品演進，Microsoft 會繼續驗證所有相關樹系都可同步處理的標準同步處理設定。 擁有自訂同步處理設定的客戶負責確保其設定會將正確的屬性和值傳送到 Azure AD。 

不論您是否有一個內部部署 Active Directory 樹系或多個樹系，Azure AD 連線可以用於各種支援的拓撲，如[Azure AD 連線拓撲](/azure/active-directory/hybrid/plan-connect-topologies)中所述。 從商務用 Skype Server 的觀點來看，有三種變化： 

1. 單一樹系，此樹系包含授權使用者身分識別，並裝載商務用 Skype Server。 

2. 多個樹系，只有其中一個樹系裝載商務用 Skype Server，另外一或多個樹系則包含授權使用者身分識別 (帳戶樹系)。 

3. 在多個樹系中部署多個商務用 Skype Server。 在符合特定需求的情況下，組織可以將多個部署合併到單一 Microsoft 365 組織。

### <a name="single-forest"></a>單一樹系 

如果使用者帳戶和商務用 Skype 全都位於單一樹系中，您必須確保將 Azure AD Connect 設定為將該樹系中的使用者同步處理到 Azure AD。  根據預設，適當的屬性會自動同步處理至 Azure Active Directory。 系統會建議客戶修改內建的同步處理規則和/或連接器，以管理不可能從安裝精靈) 中的設定 (。  

### <a name="multiple-forests-with-one-skype-for-business-deployment"></a>多個樹系與一個商務用 Skype 的部署 deployment 

此案例通常稱為「資源樹系拓撲」。 使用者的授權身分識別位於一或多個帳戶樹系中，而商務用 Skype 則部署在另一個資源樹系中 (後者本身可能也裝載授權使用者身分識別)。 一般而言，商務用 Skype 使用者的授權身分識別可以和商務用 Skype Server 位於相同樹系中，和/或位於另一個樹系中，前提是： 

- 具有帳戶樹系 (s) 中的授權身分識別的使用者，會以 (的資源樹系表示，商務用 Skype Server 部署) 為停用的使用者物件。 資源樹系中的 msRTCSIP-OriginatorSID 屬性必須與帳戶樹系中的 SID 相符。 如需詳細資訊，請參閱[設定混合式商務用 Skype 的多樹系環境](configure-a-multi-forest-environment-for-hybrid.md)。

- 裝載商務用 Skype Server 的資源樹系會信任帳戶樹系。  

- 所有來自帳戶樹系的身分識別 (相關的使用者物件和屬性) 和資源樹系) 的商務用 Skype (，都是透過 Azure AD Azure AD 與正確的值同步處理至連線。  

  若要在[多樹系內部部署案例](configure-a-multi-forest-environment-for-hybrid.md)中，將適當的物件和屬性同步處理到 Azure AD 中，Microsoft 強烈建議使用 Azure AD 連線同步處理所有已啟用使用者帳戶的樹系，以及包含商務用 Skype 的樹系。 假設您要從所有樹系進行同步處理，則必須先設定 Azure AD Connect 來合併這些身分識別，然後同步處理到 Azure AD。 Azure AD Connect 即是為了處理這種案例而設計，並在安裝精靈中提供內建選項來進行此設定，包括設定錨點以加入身分識別。 請選擇下列專案：使用者身分識別 **存在於多個目錄** 中，並 **使用--> ObjectSID 及 MsExchangeMasterAccountSID 屬性進行搭配**。


### <a name="multiple-skype-for-business-server-deployments-in-multiple-forests"></a>多個樹系中有多個商務用 Skype Server 的部署 

在此案例中，有多個樹系，每個樹系都包含商務用 Skype Server 和單一 Microsoft 365 組織。 每個包含商務用 Skype Server 的樹系，都可以使用 Azure AD 連線同步處理到該組織的 Azure AD 中。 在指定時間裡，您最多只能為商務用 Skype 混合式設定一個樹系。 在樹系中啟用混合功能之前，所有其他樹系中的所有 SIP 網域都必須使用 [停用 csonlineSipDomain](/powershell/module/skype/disable-csonlinesipdomain)加以停用。 如需詳細資訊，請參閱[Cloud 整合 for Teams 和商務用 Skype](cloud-consolidation.md)。


## <a name="related-information"></a>相關資訊

- [混合式身分識別](/azure/active-directory/hybrid/whatis-hybrid-identity)

- [Azure AD 連線 sync：瞭解和自訂同步處理](/azure/active-directory/hybrid/how-to-connect-sync-whatis)

- [Azure AD Connect 的拓撲](/azure/active-directory/hybrid/plan-connect-topologies)

- [Azure AD 連線 sync：同步處理至 Azure Active Directory 屬性](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)

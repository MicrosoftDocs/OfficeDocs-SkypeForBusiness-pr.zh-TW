---
title: 設定 Azure AD Connect
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: 在混合式環境中設定 Azure AD Connect 的指示。
ms.openlocfilehash: 75e269cfa36a97249c9078cfc37cfc493ebcc502
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780112"
---
# <a name="configure-azure-ad-connect-for-teams-and-skype-for-business"></a>針對 Teams 和商務用 Skype 設定 Configure Azure AD Connect
 
具有商務用 Skype 伺服器（或 Lync Server）內部部署的組織，以及計畫使用團隊或商務用 Skype Online 的組織，都必須設定 Azure AD Connect，以同步處理其內部部署目錄與 Office 365 （如本檔所述）。  這包括直接從商務用 Skype 內部遷移到小組的組織。 尤其是使用商務用 Skype 內部部署的組織，必須確保同步處理到 Azure AD的 msRTCSIP 屬性是正確的。 

> [!NOTE]
> 現有 Teams 使用者若同時也有商務用 Skype 內部部署，必須將其商務用 Skype 內部部署帳戶移至雲端，才能取得完整的功能，例如可與商務用 Skype 使用者互通、與同盟組織中的使用者進行通訊等功能。 即使使用者未來只會使用 Teams，基礎結構也需要此線上商務用 Skype 帳戶來提供額外的功能。  為了進行這項移轉，您必須確保已正確設定 Azure AD Connect，以便啟用混合式。
 

## <a name="background-information"></a>背景資訊

Azure Active Directory Connect 可讓您的內部部署 Active Directory 持續與 Office 365 保持同步。  您的內部部署目錄同步保留身分識別的授權來源，從您的內部部署環境所做的變更會同步處理到 Azure AD。 如需詳細資訊，請參閱[AZURE AD Connect Sync](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)。 即使您沒有將所有使用者從內部部署移至雲端，使用團隊、商務用 Skype 內部部署或商務用 Skype Online 的所有使用者，都必須從內部部署與 Azure AD 同步處理，以確保內部部署和線上使用者之間的通訊。 *在您的內部部署和線上目錄都將會表示貴組織的使用者。*


## <a name="configuring-azure-ad-when-you-have-skype-for-business-server"></a>當您有商務用 Skype Server 時設定 Azure AD 

不論您是否有一個內部部署 Active Directory 樹系或多個樹系，Azure AD Connect 都可以用於各種支援的拓撲，如[AZURE Ad connect 的拓撲](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-topologies)中所述。  從商務用 Skype Server 的角度來看，主要分成三種拓樸： 

1. 單一樹系，此樹系包含授權使用者身分識別，並裝載商務用 Skype Server。 

2. 多個樹系，只有其中一個樹系裝載商務用 Skype Server，另外一或多個樹系則包含授權使用者身分識別 (帳戶樹系)。 

3. 在多個樹系中部署多個商務用 Skype Server。 在符合特定需求的情況下，組織可以將多個部署合併到單一 Office 365 組織中。

### <a name="single-forest"></a>單一樹系 

如果使用者帳戶和商務用 Skype 全都位於單一樹系中，您必須確保將 Azure AD Connect 設定為將該樹系中的使用者同步處理到 Azure AD。  雖然 Azure AD Connect 安裝精靈有多種選項，但是適當的屬性會自動同步處理到 Azure Active Directory。 系統會建議客戶修改內建的同步處理規則和/或連接器，以管理設定（這無法從安裝精靈）。  

### <a name="multiple-forests-with-one-skype-for-business-deployment"></a>多個樹系與一個商務用 Skype 的部署 deployment 

此案例通常稱為「資源樹系拓撲」。 使用者的授權身分識別位於一或多個帳戶樹系中，而商務用 Skype 則部署在另一個資源樹系中 (後者本身可能也裝載授權使用者身分識別)。 一般而言，商務用 Skype 使用者的授權身分識別可以和商務用 Skype Server 位於相同樹系中，和/或位於另一個樹系中，前提是： 

- 在帳戶樹系中有授權身分識別的使用者，在資源樹系 (部署商務用 Skype Server) 中會表示為已停用的使用者物件，且在資源樹系中的 msRTCSIP-OriginatorSID 屬性會與帳戶樹系中的 SID 相符。 如需詳細資訊，請參閱[設定混合式商務用 Skype 的多樹系環境](configure-a-multi-forest-environment-for-hybrid.md)。

- 裝載商務用 Skype Server 的資源樹系會信任帳戶樹系。  

- 所有用於身分識別 (來自帳戶樹系) 和商務用 Skype (來自資源樹系) 的相關使用者物件和屬性，都會透過 Azure AD Connect 將適當的值同步處理到 Azure AD。  

 若要在[多樹系內部部署案例](configure-a-multi-forest-environment-for-hybrid.md)中，在 Azure ad 中取得適當的物件和屬性同步處理，Microsoft 強烈建議使用 Azure ad Connect，以同步處理已啟用使用者帳戶的所有樹系和包含商務用 Skype 的樹系。  假設您要從所有樹系進行同步處理，則必須先設定 Azure AD Connect 來合併這些身分識別，然後同步處理到 Azure AD。 Azure AD Connect 即是為了處理這種案例而設計，並在安裝精靈中提供內建選項來進行此設定，包括設定錨點以加入身分識別。  請選擇下列專案：多個目錄上都存在使用者身分識別。 搭配使用--> ObjectSID 及 msExchangeMasterAccountSID 屬性。


### <a name="multiple-skype-for-business-server-deployments-in-multiple-forests"></a>多個樹系中有多個商務用 Skype Server 的部署 

在此案例中，有多個樹系，每個樹系都包含商務用 Skype 伺服器及單一 Office 365 組織。  每個包含商務用 Skype 伺服器的樹系，都可以使用 AAD Connect 同步處理到該租使用者的 Azure AD 中。 在指定時間裡，您最多只能為商務用 Skype 混合式設定一個樹系。 在樹系中啟用混合功能之前，所有其他樹系中的所有 SIP 網域都必須使用[停用 csonlineSipDomain](https://docs.microsoft.com/powershell/module/skype/disable-csonlinesipdomain)加以停用。 如需如何將這類環境合併至 Office 365 的詳細資訊，請參閱[Cloud 整合 For 小組和商務用 Skype](cloud-consolidation.md)。

## <a name="general-requirements"></a>一般需求 

小組和商務用 Skype Online 服務都要求正確的 Active Directory 屬性存在，且已在 Azure AD 中填入。  Microsoft 的一般建議是同步處理所有包含使用者身分識別及包含商務用 Skype Server 之樹系的樹系。

 如果使用者的身分識別在多個樹系中存在，Azure AD Connect 應執行合併。 遵循此指南之後，Azure AD Connect 將會自動同步處理正確的屬性，前提是您不會在 Azure AD Connect 中修改連接器或同步規則。 
  
如果您未同步處理所有包含使用者身分識別和商務用 Skype Server 部署的樹系，則您仍然必須針對任何使用團隊或商務用 Skype （不論是內部部署或線上）的使用者，將相關的身分識別和商務用 Skype 屬性正確地填入到 Azure AD 中（不論是內部部署或線上）--可能需要其他內部部署目錄同步處理。 如需詳細資訊，請參閱[AZURE AD Connect sync：同步處理至 Azure Active Directory 的屬性](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)。

在這種情況下，客戶必須負責確保將屬性填入 Azure AD 的適當設定。 請記住下列事項： 

- 使用非標準設定來同步處理到 Azure AD 有風險，因為這可能會造成錯誤配置，而導致線上目錄中的資料損毀。

- 隨著產品演進，Microsoft 會繼續驗證所有相關樹系都可同步處理的標準同步處理設定。 擁有自訂同步處理設定的客戶負責確保其設定會將正確的屬性和值傳送到 Azure AD。 

## <a name="related-information"></a>相關資訊

- [混合式身分識別](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity?toc=%2Fen-us%2Fazure%2Factive-directory%2Fhybrid%2FTOC.json&bc=%2Fen-us%2Fazure%2Fbread%2Ftoc.json)

- [Azure AD Connect 同步處理：瞭解和自訂同步處理](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)

- [Azure AD Connect 的拓撲](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-topologies)

- [Azure AD Connect sync：同步處理至 Azure Active Directory 的屬性](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)

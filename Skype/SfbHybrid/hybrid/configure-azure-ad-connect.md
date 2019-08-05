---
title: 設定 Azure AD Connect
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: 在混合式環境中配置 Azure AD Connect 的指示。
ms.openlocfilehash: 9df0e42224d3186c3d7b5b1748412e9ec9121897
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36185482"
---
# <a name="configure-azure-ad-connect-for-teams-and-skype-for-business"></a>針對團隊和商務用 Skype 設定 Azure AD Connect
 
在內部部署使用商務用 Skype Server (或 Lync Server) 的組織, 以及規劃使用團隊或商務用 Skype Online 的組織, 都必須設定 Azure AD Connect, 以將其內部部署目錄與 Office 365 同步處理, 如以下所述單據.  這包括直接從商務用 Skype 內部部署到團隊的組織。 具體說來, 擁有商務用 Skype 內部部署的組織必須確保將適當的 msRTCSIP 屬性同步處理到 Azure AD。 

> [!NOTE]
> 您也可以將商務用 Skype 內部部署帳戶的現有團隊使用者移至雲端, 以取得完整的功能, 例如與商務用 Skype 使用者進行交互操作的功能, 以及與聯盟組織中的使用者通訊。 即使使用者只是使用團隊, 基礎結構也必須有此線上商務用 Skype 帳戶, 才能提供額外的功能。  若要進行這種遷移, 您必須確保正確設定 Azure AD Connect, 才能啟用混合式。
 

## <a name="background-information"></a>背景資訊

Azure Active Directory Connect 會讓您的內部部署 Active Directory 持續與 Office 365 保持同步。  您的內部部署目錄仍然是身分識別的授權來源, 而您內部部署環境的變更會同步處理到 Azure AD。 如需詳細資訊, 請參閱[AZURE AD Connect 同步](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/how-to-connect-sync-whatis)處理。 即使您不是將所有使用者從內部部署移至雲端, 所有使用團隊、商務用 Skype 內部部署或商務用 Skype Online 的使用者, 都必須從內部部署到 Azure AD, 以確保內部部署與線上使用者之間的通訊. *貴組織中的使用者會在您的內部部署和線上目錄中加以表示。*


## <a name="configuring-azure-ad-when-you-have-skype-for-business-server"></a>在您有商務用 Skype Server 時設定 Azure AD 

無論您有一個內部部署的 Active Directory 林或多個目錄林, Azure AD Connect 都可以在各種支援的拓撲中使用, 如[AZURE Ad connect](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/plan-connect-topologies)中的拓撲中所述。  從商務用 Skype 伺服器的角度來看, 有三種主要變化: 

1. 單一目錄林, 包含授權使用者身分識別及主機商務用 Skype 伺服器。 

2. 多個目錄林, 只有其中一個主機商務用 Skype 伺服器, 以及一或多個包含權威性使用者身分識別 (帳戶目錄林) 的其他目錄林。 

3. 多個目錄林中多個商務用 Skype Server 部署。 如果符合某些需求, 組織可以將這些多個部署整合到單一的 Office 365 租使用者。

### <a name="single-forest"></a>單一目錄林 

如果使用者帳戶和商務用 Skype 都是在單一目錄林中託管, 您必須確保 Azure AD Connect 已設定為將來自這個林的使用者同步處理到 Azure AD。  雖然 Azure AD Connect 安裝精靈有多種選項, 但適當的屬性會自動同步處理到 Azure Active Directory 中。 建議客戶不要修改內建的同步處理規則和/或連接器, 以管理設定 (這是無法從安裝精靈進行的)。  

### <a name="multiple-forests-with-one-skype-for-business-deployment"></a>多個目錄林且有一個商務用 Skype 部署 

這個案例通常稱為資源林拓撲。 使用者的授權身分識別是託管在一個或多個帳戶目錄林中, 而商務用 Skype 則會部署在另一個資原始目錄林中 (本身也可能會主持權威性的使用者身分識別)。 一般來說, 商務用 Skype 使用者的授權身分識別可以與商務用 Skype 伺服器和/或其他林中的同一個林中, 提供: 

- 從帳戶目錄林中擁有權威性身分識別身分識別的使用者會以停用的使用者物件的形式, 在資原始目錄林中 (部署商務用 Skype 伺服器的位置) 表示, 而資源林中的 msRTCSIP-OriginatorSID 屬性則與帳戶目錄林。 如需詳細資訊, 請參閱[設定混合式商務用 Skype 的多林環境](configure-a-multi-forest-environment-for-hybrid.md)。

- 主持商務用 Skype Server 的資原始目錄林信任帳戶目錄林。  

- 針對身分識別 (來自帳戶林) 與商務用 Skype (來自資源林) 的所有相關使用者物件和屬性, 都是透過 Azure AD Connect 與正確的值同步處理到 Azure AD。  

 若要在[多目錄林內部部署案例](configure-a-multi-forest-environment-for-hybrid.md)中, 在 Azure AD 中實現適當的物件和屬性同步處理, Microsoft 強烈建議您使用 Azure AD Connect 從已啟用使用者帳戶的所有目錄林, 以及包含商務用 Skype。  如果您是從所有的目錄林進行同步處理, 則必須設定 Azure AD Connect 來合併這些身分識別, 並同步處理到 Azure AD。 Azure AD Connect 的設計目的是處理這個案例, 並提供安裝精靈中的內建選項來設定此情況, 包括設定加入身分識別的錨點。  選擇下列專案: 多個目錄中都存在使用者身分識別。 搭配使用--> ObjectSID 和 msExchangeMasterAccountSID 屬性。


### <a name="multiple-skype-for-business-server-deployments-in-multiple-forests"></a>多個林中的多個商務用 Skype Server 部署 

在此案例中, 有多個目錄林, 每個都包含商務用 Skype 伺服器以及單一的 Office 365 租使用者。  每個包含商務用 Skype 伺服器的林中, 都可以使用 AAD Connect 同步處理到該租使用者的 Azure AD 中。 在特定時間, 您最多隻能針對商務用 Skype 混合式設定一個目錄林。 在林中啟用混合功能之前, 必須使用[disable-csonlineSipDomain](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain)停用所有其他目錄林的所有 SIP 網域。 如需如何將此類環境合併至 Office 365 的詳細資訊, 請參閱[小組和商務用 Skype 的雲端整合](cloud-consolidation.md)。

## <a name="general-requirements"></a>一般需求 

[小組] 和 [商務用 Skype] 線上服務都要求正確的 Active Directory 屬性存在, 且已填入 Azure AD。  Microsoft 的一般建議是同步處理所有包含使用者身分識別的目錄林, 以及包含商務用 Skype 伺服器的任何目錄林。

 如果有多個目錄林的使用者身分識別, Azure AD Connect 應該會進行合併。 遵循本指南之後, 只要您不在 Azure AD Connect 中修改連接器或同步處理規則, Azure AD Connect 就會自動同步處理正確的屬性。 
  
如果您不是從所有包含使用者身分識別及商務用 Skype Server 部署的目錄林進行同步處理, 您仍然必須確保針對使用團隊或 Skype 的任何使用者將相關身分識別與商務用 Skype 屬性正確填入 Azure AD。商務 (無論是內部部署或線上))--這可能需要額外的內部部署目錄同步處理。 如需詳細資訊, 請參閱[AZURE AD Connect 同步處理: 屬性已同步處理到 Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)。

在這種情況下, 客戶必須負責確保將屬性填入 Azure AD 所需的適當配置。 請記住下列事項: 

- 使用非標準的設定來同步處理到 Azure AD 是危險的, 因為這可能會導致無法正確配置, 可能會導致您的線上目錄中的資料損毀。

- 隨著產品不斷演化, Microsoft 會繼續驗證已同步處理所有相關目錄林的標準同步處理設定。 具有自訂同步處理設定的客戶負責確保其設定能將正確的屬性和值傳遞到 Azure AD。 

## <a name="related-information"></a>相關資訊

- [什麼是混合式身分識別](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/whatis-hybrid-identity?toc=%2Fen-us%2Fazure%2Factive-directory%2Fhybrid%2FTOC.json&bc=%2Fen-us%2Fazure%2Fbread%2Ftoc.json)

- [Azure AD Connect 同步處理: 瞭解及自訂同步處理](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/how-to-connect-sync-whatis)

- [Azure AD Connect 的拓撲](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/plan-connect-topologies)

- [Azure AD Connect 同步處理: 屬性已同步處理到 Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)

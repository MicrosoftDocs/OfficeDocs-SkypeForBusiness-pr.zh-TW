---
title: 管理貴組織的電話號碼
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: davlick, roykuntz, jenstr
ms.topic: conceptual
ms.assetid: 6b61cb3c-361c-48a8-a9ef-d81bddde27bb
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.phonenumbers.overview
- ms.teamsadmincenter.voice.searchandacquire.PSTNpartner
- ms.lync.lac.NewNumberManualAcquisitionOpenSupportTicket
- ms.lync.lac.VASAMissingGeoCodes
- Calling Plans
- seo-marvel-apr2020
description: 瞭解如何為貴組織取得及管理使用者 () 與服務 (Microsoft Teams 的付費和免付費) 電話號碼。
ms.openlocfilehash: 15caaa7b5d21ae86d0b0079aeb743690294fd85b
ms.sourcegitcommit: 3f6ae7946b64e857f6358019be2f0fdf19a207ad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/29/2022
ms.locfileid: "67074671"
---
# <a name="manage-telephone-numbers-for-your-organization"></a>管理組織的電話號碼

目前，Microsoft 支援兩種電話號碼類型： 

- [**使用者號碼**](#user-telephone-numbers)，也稱為訂閱者號碼，可以指派給您組織中的使用者。

- [**服務號碼**](#service-telephone-numbers)，指派給服務，例如 [音訊會議](deploy-audio-conferencing-teams-landing-page.md)、 [自動語音應](plan-auto-attendant-call-queue.md)答或 [通話佇列](plan-auto-attendant-call-queue.md)。

Microsoft 正在努力簡化數位類型，但現在您必須決定：

- 哪些使用者位置需要 Microsoft 的新電話號碼？
- 我需要訂閱者或服務 (電話號碼類型) ？
- 如何?將現有的電話號碼移轉到 Teams 嗎？

您取得及管理電話號碼的方式會根據您的公用交換電話網路 (PSTN) 連線選項而有所不同。

- 如需管理 Microsoft 通話方案電話號碼的相關資訊，請參閱 [管理通話方案的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。

- 如需管理運算子連線電話號碼的相關資訊，請參閱 [使用運算子連線設定電話號碼](operator-connect-configure.md#set-up-phone-numbers)。

- 如需管理直接路由之電話號碼的相關資訊，請參閱設定 [電話號碼並啟用企業語音](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice)。


> [!NOTE]
> 如果您需要 Microsoft Teams 系統管理中心所顯示號碼以外的其他號碼類型或其他號碼類型，您可以將電話號碼要求提交至 [電話號碼服務中心](https://pstnsd.powerappsportals.com/)。

## <a name="user-telephone-numbers"></a>使用者電話號碼

使用者電話號碼有兩種類型，可以指派給組織中的使用者：  
    
- **地理數位** 與地理區域具有關聯性，且最為常見。 例如，大部分情況下的地理電話號碼只能用於國家/地區的特定位址、縣/市、州或地區。
    
- **非地理位置的數位** 稱為國家/地區號碼，有時稱為 VoIP 數位。 這些數位與國家/地區的地理區域沒有關聯。 例如，從國家/地區內的任何位置撥打號碼時，非地理位置號碼的成本通常相同。 此外，某些國家，例如丹麥，只有非地理位置的數位可供使用。


## <a name="service-telephone-numbers"></a>服務電話號碼  

本節說明您的授權中所提供的 Microsoft 服務號碼。 如需運算子連線或直接路由所提供的服務號碼的相關資訊，請連絡您的提供者。 

Microsoft 提供的服務電話號碼有兩種類型：付費和免付費電話，可以指派給音訊會議、自動語音應答或通話佇列等服務。 與使用者號碼相比，服務號碼的並行通話容量較高。 服務號碼可用性會因國家/地區和號碼類型而有所不同， (是付費號碼或免付費電話號碼) 。 Microsoft 在每個國家/地區的電話語音授權會聽寫該號碼的用途。
    
 - **付費服務號碼** - 有兩種類型的付費服務號碼，可能會對來電者產生付費費用：
    
   - **地理數位** 地理數位與地理區域有關聯。 例如，大部分情況下的地理電話號碼只能用於國家/地區的特定位址、縣/市、州或地區。
        
   - **非地理位置的數位** 非地理位置的數位是指與國家/地區內的地理區域沒有關聯的國數位。 例如，從國家/地區內的任何位置撥打號碼時，非地理位置號碼的成本通常相同。
   
- **免付費服務號碼** - 這些服務號碼通常不會對來電者產生付費費用。 Teams 提供 60 多個國家/地區的國家/地區免付費電話號碼。
    
    > [!CAUTION]
    > 在某些情況下，某些國家/地區和原始號碼類型，例如來自行動電話的通話，可能會對來電者產生付費費用。 

## <a name="where-phone-numbers-are-managed"></a>管理電話號碼的位置

管理數位的位置和方式取決於 PSTN 連線選項：

- Microsoft 通話方案和運算子連線電話號碼只能在 Microsoft 365 中管理。

- 您可以在 內部部署的 Active Directory 或 Microsoft 365 中管理直接路由電話號碼，如下一節所述。

### <a name="direct-routing-numbers-managed-in-an-on-premises-active-directory"></a>在內部部署的 Active Directory中管理的直接路由號碼

如果您有或有商務用 Skype Server混合式部署，您的內部部署的 Active Directory很可能是與 Microsoft 365 同步處理。 這表示使用者和資源帳戶上的目錄屬性是在內部部署的 Active Directory中管理，並同步處理到 Microsoft 365。

如果直接路由電話號碼是在內部部署的 Active Directory的使用者或資源帳戶上管理，則帳戶上的 msRTCSIP-Line 參數會包含值。 您可以使用 ADSI 編輯等工具，檢視指派給內部部署的 Active Directory之使用者或資源帳戶的 msRTCSIP-Line 參數。   

當此參數透過目錄同步處理常式 (Azure AD Connect) 自動同步處理到 Microsoft 365 中的使用者或資源帳戶之後，您可以檢視 [Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser) Cmdlet 輸出中的 OnPremLineURi 參數來檢視電話號碼。

| 哪裡 | 參數 | 值 |
| :------------| :-------| :---------|
| 內部部署 AD | msRTCSIP-Line | tel：+14255551234 |
| Microsoft 365 | OnPremLineURi | tel：+14255551234 |

### <a name="direct-routing-numbers-managed-in-microsoft-365"></a>在 Microsoft 365 中管理的直接路由號碼

如果您不是管理內部部署的 Active Directory中的直接路由電話號碼，則會在 Microsoft 365 中管理。 由於電話號碼未與 Microsoft 365 同步，因此在使用者或資源帳戶執行的 Get-CsOnlineUser Cmdlet 輸出中，OnPremLineUri 參數中不會顯示這些號碼。

### <a name="direct-routing-numbers-managed-in-both-an-on-premises-active-directory-and-microsoft-365"></a>在 內部部署的 Active Directory 和 Microsoft 365 中管理的直接路由號碼

您可以在內部部署的 Active Directory中管理部分使用者和資源帳戶的直接路由電話號碼，以及在 Microsoft 365 中管理其他帳戶的直接路由電話號碼。 此功能取決於屬性 msRTCSIP-Line 是在內部部署的 Active Directory的使用者帳戶或資源帳戶上設定。    

### <a name="change-where-direct-routing-phone-numbers-are-managed"></a>變更管理直接路由電話號碼的位置

若要變更管理直接路由電話號碼的位置，您必須從使用者的 msRTCSIP-Line 屬性移除電話號碼，或移除內部部署的 Active Directory中的 resouce 帳戶。   

如需詳細資訊，請參閱[清除 Active Directory 中所有內部部署使用者的商務用 Skype屬性](/skypeforbusiness/hybrid/cloud-consolidation-managing-attributes#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory.md)。 請注意，電話號碼必須重新指派給 Microsoft 365 中的使用者或資源帳戶。

移除專案與 Microsoft 365 同步處理之後，使用者或資源帳戶上Get-CsOnlineUser輸出中的 OnPremLineUri 屬性將會是空白的。 


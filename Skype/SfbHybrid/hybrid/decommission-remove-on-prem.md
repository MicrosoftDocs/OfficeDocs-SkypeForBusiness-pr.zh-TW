---
title: 解除委任商務用 Skype Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
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
description: 解除委任商務用 Skype Server 的指示。
ms.openlocfilehash: fd2ba8543745760e900e52c2c1f9b3c3f65b0e70
ms.sourcegitcommit: b17e5acadcca0261eaccc64e1b4ee457348f975c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/17/2021
ms.locfileid: "58365620"
---
# <a name="remove-your-on-premises-skype-for-business-deployment"></a>移除您的內部部署商務用 Skype 部署

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

本文說明如何移除內部部署商務用 Skype 部署。 這是下列步驟的步驟4，以解除委任您的內部部署環境：

- 步驟 1. [將所有必要使用者從內部部署移至線上](decommission-move-on-prem-users.md)。 

- 步驟 2： [停用您的混合](cloud-consolidation-disabling-hybrid.md)式設定。

- 步驟 3. [從內部部署向線上遷移混合應用程式端點](decommission-move-on-prem-endpoints.md)

- **步驟4。移除您的內部部署商務用 Skype 部署。**  (本文) 


> [!IMPORTANT] 
> 本文中的步驟僅適用于使用方法2管理使用者屬性時[，如下所述。](cloud-consolidation-managing-attributes.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory) 如果您是使用方法1，請勿使用本文所述的步驟來移除您的商務用 Skype 伺服器。 相反地，您可以重新鏡像伺服器。

若要完成本文中的步驟，您需要具備 Schema Admins 群組和 Enterprise 系統管理員群組的許可權。 您將需要這些許可權，才能撤銷 Active Directory 網域服務的商務用 Skype Server 架構和樹系層級變更。 您也必須是 RTCUniversalServerAdmins 群組的成員。


## <a name="prepare-to-remove-the-skype-for-business-deployment"></a>準備移除商務用 Skype 部署

將所有必要的使用者帳戶移至雲端後，可能仍然會有一些其他的內部部署物件，例如您將需要清理的連絡人和應用程式。

使用下列步驟來清除這些物件，並確定您同時是本機系統管理員群組和 RTCUniversalServerAdmins 群組的成員。 請注意，商務用 Skype Server 2019 中無法使用 ExUmContacts 和 PersistantChatEndPoints。 如果您有商務用 Skype Server 2019，應省略下列步驟中的對應 Cmdlet。

1. 若要檢查是否有任何與商務用 Skype Server 內部部署相關聯的連絡人或應用程式，請執行下列商務用 Skype Server PowerShell Cmdlet。

   ```PowerShell
   Get-CsMeetingRoom
   Get-CsCommonAreaPhone
   Get-CsAnalogDevice
   Get-CsExUmContact
   Get-CsDialInConferencingAccessNumber
   Get-CsRgsWorkflow
   Get-CsTrustedApplicationEndpoint
   Get-CsTrustedApplication
   Get-CsPersistentChatEndpoint
   Get-CsAudioTestServiceApplication
   Get-CsCallParkOrbit
   Get-CsUnassignedNumber
   ```
2. 從步驟1中的 Cmdlet 複查輸出清單。 然後，如果可以移除物件，請執行下列商務用 Skype Server PowerShell Cmdlet：

   ```PowerShell
   Get-CsMeetingRoom | Disable-CsMeetingRoom
   Get-CsCommonAreaPhone | Remove-CsCommonAreaPhone 
   Get-CsAnalogDevice | Remove-CsAnalogDevice
   Get-CsExUmContact | Remove-CsExUmContact
   Get-CsDialInConferencingAccessNumber | Remove-CsDialInConferencingAccessNumber
   Get-CsRgsWorkflow | Remove-CsRgsWorkflow
   Get-CsTrustedApplicationEndpoint | Remove-CsTrustedApplicationEndpoint
   Get-CsTrustedApplication | Remove-CsTrustedApplication -Force
   Get-CsPersistentChatEndpoint |  Remove-CsPersistentChatEndpoint
   Get-CsCallParkOrbit | Remove-CsCallParkOrbit -Force
   Get-CsVoiceRoute | Remove-CsVoiceRoute -Force
   Get-CsUnassignedNumber | Remove-CsUnassignedNumber -Force
   ```
## <a name="remove-your-on-premises-skype-for-business-deployment"></a>移除您的內部部署商務用 Skype 部署

完成所有初步步驟之後，您可以遵循下列步驟移除商務用 Skype 部署：

1. 從邏輯上移除商務用 Skype Server 部署，但單一前端除外，如下所示：

   1. 更新您的商務用 Skype Server 拓撲，使其具有單一前端集區：

      1. 在 [拓撲產生器] 中，下載新的複本並流覽至前端集區。
      1. 以滑鼠右鍵按一下集區，然後按一下 [編輯屬性]。
      1. 在 [ **關聯**] 中，取消選取媒體元件的 [ **建立 Edge 集** 區 (]) 然後按一下 **[確定]**。
      1. 如果有一個以上的前端集區，請移除所有剩餘集區的關聯。
      1. 選取 [ **動作] > [移除部署**]。
      1. 選取 [ **動作] > [發行拓撲**]。

    1. 發行拓撲之後，請完成嚮導中所述的其他步驟。

2. 執行下列商務用 Skype Server PowerShell Cmdlet 來移除商務用 Skype Server 會議目錄：

   ```PowerShell
   Get-CsConferenceDirectory | Remove-CsConferenceDirectory -Force
   ```

3. 執行下列商務用 Skype Server PowerShell Cmdlet，以完成商務用 Skype Server 部署的卸載：

   ```PowerShell
   Publish-CsTopology -FinalizeUninstall
   ```
   > [!NOTE]
   > 如果此步驟傳回錯誤，請開啟 Microsoft 支援票證以取得刪除剩餘的陳舊物件的說明。

4. 執行下列商務用 Skype Server PowerShell Cmdlet，以移除中央管理存放區服務控制點：

   ```PowerShell
   Remove-CsConfigurationStoreLocation
   ``` 

5. 執行下列商務用 Skype Server PowerShell Cmdlet 以復原商務用 Skype Server Active Directory 網域層級變更：

   ```PowerShell
   Disable-CsAdDomain
   ```
6. 執行下列商務用 Skype Server PowerShell Cmdlet 以復原商務用 Skype Server Active Directory 樹系層級變更。

   ```PowerShell
   Disable-CsAdForest
   ```

## <a name="see-also"></a>另請參閱

- [解除您的內部部署商務用 Skype 環境](decommission-on-prem-overview.md)

- [將所有必要使用者從內部部署移至線上](decommission-move-on-prem-users.md)

- [停用混合式設定](cloud-consolidation-disabling-hybrid.md)

- [將混合應用程式端點從內部部署移至線上](decommission-move-on-prem-endpoints.md)


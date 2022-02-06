---
title: 封存組態
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.lscp.MonArchSettingMain
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 9c2fd164-a9b8-40e6-a1c4-423a7fe34aba
description: 您可以使用封存設定來控制商務用 Skype Server 部署的封存選項，包含啟用及停用下列選項：
---

# <a name="archiving-configuration"></a>封存組態
 
您可以使用封存設定來控制商務用 Skype Server 部署的封存選項，包含啟用及停用下列選項：
  
- 封存失敗時封鎖立即訊息 (IM) 或會議會話
    
- 與 Exchange 2013 storage 整合，供位於 Exchange 2013 的使用者使用
    
- 清除封存的資料
    
封存設定包括全域設定，以及選擇性地包含一或多個網站與集區封存設定：
  
- **通用** 設定預設會在所有的商務用 Skype Server 部署中建立全域設定。 您可以編輯全域設定，但無法刪除此封存設定。 若嘗試將其刪除，所有選項都會重設為預設值。
    
- **網站設定 (選用)** 您可以指定一或多個網站封存設定，每個網站封存設定可用於控制特定網站的封存選項。 網站設定會覆寫全域設定，但僅限於在封存網站設定中指定的網站。 您可以編輯或刪除網站設定。
    
- 集區設定 **(選用)** 您可以指定一或多個集區封存設定，以控制特定集區的封存選項。 集區設定優先於全域設定與網站設定，但僅限於封存集區設定中所指定的集區。 您可以編輯或刪除集區設定。
    
> [!NOTE]
> 封存設定會套用至位於商務用 Skype Server 的使用者，而且如果您使用 Exchange 將 Microsoft Exchange 中的封存資料儲存到 Exchange 2013 的使用者，但為位於 Exchange 2013 的使用者，執行方式會稍有不同。 其差異會在下一節中說明。 
  
**[封存** 設定] 頁面會列出為您的部署設定的每個封存原則。 它也會顯示原則名稱、範圍 (全域、網站或集區) ，以及針對每個封存設定啟用的封存選項。 在 [封存設定 **] 頁面上** ，您可以使用下列選項：
- **新增功能** 您可以新增一或多個下列選用的封存設定。
    
  - 網站設定
    
  - 集區設定
    
- **編輯** 您可以變更頁面上所列之任何封存設定的選項。 使用此選項，您可以執行下列作業：
    
  - **顯示詳細資料** 此選項會開啟對話方塊，您可以在其中變更所選封存設定的封存選項。 您一次只能顯示一個封存設定的詳細資料。
    
  - **全選** 此選項會選取清單中的所有封存設定。
    
  - **刪除** 此選項會刪除所有選取的封存設定。
    
- **行動** 您可以使用此選項，快速啟用或停用頁面上所列之任何設定中的 IM 會話或 web 會議會話的封存，而不是編輯設定。 [ **動作** ] 下的可用選項取決於目前在封存設定中指定的選項。 所有選項均可使用，但目前針對封存設定所作用的選項除外。 選項包括下列各項：
    
  - **封存 IM 工作階段**
    
  - **封存 IM 和 Web 會議工作階段**
    
  - **停用封存**
    
- **刷新** 您可以重新整理「封存設定 **」頁面，** 以確認所有封存設定之選項的狀態。
    
如需封存功能及功能的詳細資料，包括 Exchange 整合，請參閱[在商務用 Skype Server 2015 中規劃](../../plan-your-deployment/archiving/archiving.md)封存、[部署商務用 Skype Server 2015 的](../../deploy/deploy-archiving/deploy-archiving.md)封存，以及[管理商務用 Skype Server 2015 中](../../manage/archiving/archiving.md)的封存。


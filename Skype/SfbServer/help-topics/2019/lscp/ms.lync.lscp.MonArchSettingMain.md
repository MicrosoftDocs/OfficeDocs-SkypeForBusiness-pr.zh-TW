---
title: 封存組態
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.MonArchSettingMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 9c2fd164-a9b8-40e6-a1c4-423a7fe34aba
ROBOTS: NOINDEX, NOFOLLOW
description: 您可以使用封存配置來控制商務用 Skype Server 部署的封存選項，包括啟用和停用下列選項：
ms.openlocfilehash: 35ef51f9e67b42624dbf106037ae6a57343c21c1
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41795012"
---
# <a name="archiving-configuration"></a>封存組態
 
您可以使用封存配置來控制商務用 Skype Server 部署的封存選項，包括啟用和停用下列選項：
  
- 若封存失敗，封鎖立即訊息 (IM) 或會議工作階段
    
- 與 Exchange 存儲整合，適用于駐留在 Exchange 的使用者
    
- 清除封存資料
    
封存組態包含全域組態以及選用的一或多個網站與集區封存組態：
  
- **全域配置**預設會在所有商務用 Skype Server 部署中建立全域配置。 您可以編輯全域組態，但無法刪除此封存組態。 如果嘗試刪除此原則，則所有選項會重設為預設值。
    
- **網站設定（選用）** 您可以指定一個或多個網站歸檔設定，每個設定都可以設定以控制特定網站的封存選項。 網站組態會覆寫全域組態，但僅限於該封存網站組態中指定的網站。 您可以編輯或刪除網站組態。
    
- **池配置（選用）** 您可以指定一個或多個池存檔設定，以控制特定池的存檔選項。 集區組態會覆寫全域組態及網站組態，但僅限於在封存集區組態中指定的集區。 您可以編輯或刪除集區組態。
    
> [!NOTE]
> 封存設定適用于駐留在商務用 Skype Server 的使用者，而且如果您使用 Exchange 將存檔資料儲存在 Microsoft Exchange 中，請移至駐留在 Exchange 的使用者，但在 Exchange 中的使用者的執行方式稍有不同。 下一節將說明此不同之處。 
  
「封存組態」**** 頁面列出針對您部署所設定的每個封存原則。該頁面也會顯示原則名稱、範圍 (全域、網站或集區)，以及已針對每個封存組態啟用的封存選項。您可從「封存組態」**** 頁面執行下列選項：
- **新增**您可以新增下列其中一或多個選用的存檔設定。
    
  - 網站組態
    
  - 集區組態
    
- [**編輯**]您可以變更頁面上所列的任何存檔設定選項。 使用此選項，您可以執行下列動作：
    
  - **顯示詳細資料**這個選項會開啟一個對話方塊，您可以在其中變更所選封存設定的 [封存] （存檔）選項。 您一次只能顯示一個存檔設定的詳細資料。
    
  - **選取全部**此選項會選取清單中的所有存檔設定。
    
  - **刪除**此選項會刪除所有選取的存檔設定。
    
- **動作**您可以使用這個選項，在頁面上所列的任何設定中快速啟用或停用 IM 會話或網路會議會話的存檔，而不是編輯設定。 [**動作**] 底下的可用選項，取決於存檔設定中目前指定的選項。 您可以使用所有選項，除了目前對封存設定有效的選項。 選項包括下列各項：
    
  - **封存 IM 工作階段**
    
  - **封存 IM 與 Web 會議工作階段**
    
  - **停用封存**
    
- **更新**您可以重新整理 **[封存**設定] 頁面，以驗證所有存檔設定的選項狀態。
    
如需有關存檔功能和功能（包括 Exchange 整合）的詳細資料，請參閱[在商務用 Skype server 中進行](../../../plan-your-deployment/archiving/archiving.md)封存、[部署商務用 skype server](../../../deploy/deploy-archiving/deploy-archiving.md)的封存，以及[管理商務用 skype 伺服器](../../../manage/archiving/archiving.md)的封存。


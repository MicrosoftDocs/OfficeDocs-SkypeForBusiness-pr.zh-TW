---
title: 設定商務用 Skype Server 與 Exchange storage 的整合
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: 摘要：閱讀此主題以瞭解如何在商務用 Skype Server 中設定與 Exchange 儲存區的整合。
ms.openlocfilehash: 05a0c65aaca54e469f30dd5e732565f6ec0bbb4b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825063"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a>設定商務用 Skype Server 與 Exchange storage 的整合
 
**摘要：** 閱讀此主題以瞭解如何在商務用 Skype Server 中設定與 Exchange 儲存區的整合。
  
如果您部署中的所有使用者都使用 Microsoft Exchange 整合，您就不需要為使用者設定商務用 Skype Server 封存原則。 相反地，您可以設定 Exchange In-Place 保留原則，以支援駐留在 Exchange 上之使用者的封存，並將其信箱置於 In-Place 保留狀態。 設定與 Exchange storage 的整合之前，請先閱讀封存中的封存以進行 [商務用 Skype Server](../../plan-your-deployment/archiving/archiving.md)。 如需 Exchange In-Place 保留原則的詳細資訊，請參閱 Exchange 產品檔。 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a>設定與 Microsoft Exchange storage 的整合

1. 使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。
    
2. 開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。 
    
3. 在左導覽列中 **，按一下 [****監視與** 封存]，然後按一下 [封存設定]。
    
4. 按一下封存組態清單中適當的全域、網站或集區組態名稱，再依序按一下 [編輯] 和 [顯示詳細資料]，然後執行下列作業：
    
   - 若要啟用與 Exchange 存放區的整合，請選取 [ **Microsoft Exchange 整合** ] 核取方塊。
    
   - 若要停用 Exchange 存放區的整合，請清除 [ **Microsoft Exchange 整合** ] 核取方塊。
    
5. 按一下 **[認可]**。
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a>在不同樹系中部署商務用 Skype Server 和 Microsoft Exchange 時

如果您使用 Microsoft Exchange 整合，而且 Microsoft Exchange Server 與商務用 Skype Server 不在相同樹系中，您必須確定下列 Exchange Active Directory 屬性已同步處理至部署商務用 Skype 伺服器的樹系：
  
- msExchUserHoldPolicies
    
- proxyAddresses
    
此為多重值屬性。在同步處理此屬性之時，您必須將數值合併，不要予以取代，以便確保現有數值不會遺失。
  


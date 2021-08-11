---
title: 設定商務用 Skype Server 的 Exchange 儲存裝置的整合
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
description: 摘要：閱讀此主題以瞭解如何設定商務用 Skype Server 中的 Exchange 儲存裝置的整合。
ms.openlocfilehash: e33c5fcfb4ff059a266abbd06f31674e753ba1efb16b094244cba4e1f333c098
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54312091"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a>設定商務用 Skype Server 的 Exchange 儲存裝置的整合
 
**摘要：** 閱讀此主題以瞭解如何設定商務用 Skype Server 中的 Exchange 儲存裝置的整合。
  
如果您使用 Microsoft Exchange 整合部署中的所有使用者，您就不需要為使用者設定商務用 Skype Server 的封存原則。 相反地，您可以設定 Exchange In-Place 保留原則，以支援位於 Exchange 上之使用者的封存，且其信箱置於 In-Place 保留狀態。 設定與 Exchange 儲存的整合之前，請先[在商務用 Skype Server 中封存的封存方案](../../plan-your-deployment/archiving/archiving.md)。 如需 Exchange In-Place 保留原則的詳細資訊，請參閱 Exchange 產品檔。 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a>設定與 Microsoft Exchange 儲存區的整合

1. 使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。
    
2. 開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 
    
3. 在左導覽列中 **，按一下 [****監視與** 封存]，然後按一下 [封存設定]。
    
4. 按一下封存組態清單中適當的全域、網站或集區組態名稱，再依序按一下 [編輯] 和 [顯示詳細資料]，然後執行下列作業：
    
   - 若要啟用與 Exchange 儲存區的整合，請選取 [ **Microsoft Exchange 整合**] 核取方塊。
    
   - 若要停用 Exchange 儲存的整合，請清除 [ **Microsoft Exchange 整合**] 核取方塊。
    
5. 按一下 **[認可]**。
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a>在不同樹系中部署商務用 Skype Server 和 Microsoft Exchange 時

[！注意] 如果您使用 Microsoft Exchange 整合，而且 Microsoft Exchange Server 與商務用 Skype Server 部署在相同樹系中，您必須確定下列的 Exchange Active Directory 屬性已同步處理至部署商務用 Skype Server 的樹系：
  
- msExchUserHoldPolicies
    
- proxyAddresses
    
此為多重值屬性。在同步處理此屬性之時，您必須將數值合併，不要予以取代，以便確保現有數值不會遺失。
  


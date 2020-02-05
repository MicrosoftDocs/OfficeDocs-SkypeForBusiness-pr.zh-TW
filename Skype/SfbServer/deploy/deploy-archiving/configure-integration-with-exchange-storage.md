---
title: 針對商務用 Skype Server 設定與 Exchange storage 整合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: 摘要：請閱讀本主題，以瞭解如何在商務用 Skype Server 中設定與 Exchange 儲存體的整合。
ms.openlocfilehash: cee41a52593a90490ec8da90637ee4ec5de33d03
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768886"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a>針對商務用 Skype Server 設定與 Exchange storage 整合
 
**摘要：** 請閱讀本主題，以瞭解如何在商務用 Skype Server 中設定與 Exchange 儲存體的整合。
  
如果您針對部署中的所有使用者使用 Microsoft Exchange 整合，就不需要針對使用者設定商務用 Skype Server 封存原則。 相反地，您可以設定 Exchange 就地保留原則，以支援駐留在 Exchange 的使用者的封存，且其信箱會放入就地保留。 在您設定與 Exchange 儲存體的整合之前，請先閱讀[商務用 Skype Server 中的封存方案](../../plan-your-deployment/archiving/archiving.md)。 如需 Exchange 就地保留原則的詳細資訊，請參閱 Exchange 產品檔。 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a>設定與 Microsoft Exchange 儲存空間的整合

1. 從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。
    
2. 開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。 
    
3. 在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [封存**配置**]。
    
4. 在歸檔設定清單中，按一下適當的全域、網站或池設定的名稱，按一下 [**編輯**]，按一下 [**顯示詳細資料**]，然後執行下列動作：
    
   - 若要啟用與 Exchange 儲存體的整合，請選取 [ **Microsoft Exchange 整合**] 核取方塊。
    
   - 若要停用 Exchange 儲存體整合，請清除 [ **Microsoft Exchange 整合**] 核取方塊。
    
5. 按一下 [認可]****。
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a>商務用 Skype Server 和 Microsoft Exchange 部署在不同的林中

如果您使用的是 Microsoft Exchange 整合，而且 Microsoft Exchange Server 與商務用 Skype Server 不在同一個林中，您必須確認下列 Exchange Active Directory 屬性已同步處理至 Skype 適用的林中已部署商務伺服器：
  
- msExchUserHoldPolicies
    
- proxyAddresses
    
這是多重值屬性。 同步處理此屬性時，您必須合併值，而不要將其取代，以確保現有值不會遺失。
  


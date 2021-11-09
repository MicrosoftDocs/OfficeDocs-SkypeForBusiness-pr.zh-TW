---
title: 在商務用 Skype Server 中建立新的 PIN 原則
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 8bdf0478-fe9f-4371-93ff-db39381a25db
description: 摘要：在商務用 Skype Server 中建立新的 PIN 原則。
ms.openlocfilehash: cf9a35c634c9b53b557601009fa131c3c24e7db2
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60844206"
---
# <a name="create-a-new-pin-policy-in-skype-for-business-server"></a>在商務用 Skype Server 中建立新的 PIN 原則
 
**摘要：** 在商務用 Skype Server 中建立新的 PIN 原則。
  
您可以使用 [ **PIN 原則**] 頁面，提供個人識別碼 (PIN) 驗證，以供使用 IP 電話連線至商務用 Skype 的使用者使用。 若要使用 PIN 驗證，請確定已在 Web 服務設定中選取了 [啟用 PIN 驗證]。
  
請遵循下列步驟建立使用者層級或網站層級的 PIN 原則。 
  
### <a name="to-create-a-user-or-site-pin-policy"></a>建立使用者或網站 PIN 原則

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署商務用 Skype Server 之網路中的任何電腦。
    
2. 開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 
    
3. 在左導覽列中，依序按一下 [安全性] 和 [PIN 原則]。
    
4. 在 [ **PIN 原則** ] 頁面上，按一下 [ **新增**]，然後執行下列其中一項動作：
    
   - 若要建立使用者層級原則，請按一下 [ **使用者原則**]。 在 [ **新增 PIN 原則**] 的 [ **名稱**] 中，輸入描述原則的名稱。
    
   - 若要建立網站層級原則，請按一下 [ **網站原則**]。 在 [ **選取網站** ] 搜尋欄位中，輸入您要建立原則的網站名稱全部或部分名稱。 在產生的網站清單中，按一下您想要的網站，然後按一下 **[確定]**。
    
5. 在 [ **描述** ] 欄位中，輸入 PIN 原則的描述。
    
6. 在 [ **最小 PIN 碼長度** ] 欄位中，輸入或選取您想要允許的最小 pin 碼長度。 預設的最小長度為五位數。
    
7. 若要能夠指定使用者遭鎖定前可嘗試登入的次數上限，請選取 **[指定登入嘗試次數上限]** 核取方塊。若未選取此選項，則會根據 PIN 長度自動指定允許的嘗試次數上限。依預設會自動指定嘗試次數上限。
    
8. 如果您選取了 **[指定登入嘗試次數上限]** 核取方塊，請在 **[登入嘗試次數上限]** 中輸入或選取您所要允許的登入嘗試次數上限。
    
9. 若要讓 PIN 有期限，請選取 **[啟用 PIN 到期]** 核取方塊。若未選取此選項，PIN 將永不過期。根據預設，PIN 永遠不會過期。
    
10. 如果您選取了 **[啟用 PIN 到期]** 核取方塊，請在 **[PIN 於下列日數後到期]** 中輸入或選取 PIN 將在幾天之後到期。
    
11. 在 **[PIN 碼歷程記錄計數]** 中，輸入使用者必須在建立多少個 PIN 之後才可重複使用 PIN。根據預設，使用者可重複使用其 PIN。
    
12. 若要允許 Pin 碼的一般模式，例如 "1234" 和 "8888"，請選取 [ **允許共同模式** ] 核取方塊。 若未選取此選項，則只會允許複合模式的數字。 依預設只會允許複合模式的數字。
    
    > [!IMPORTANT]
    > 建議您不要允許共同模式。 
  
13. 按一下 **[認可]**。
    


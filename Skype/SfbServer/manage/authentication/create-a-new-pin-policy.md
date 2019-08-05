---
title: 在商務用 Skype Server 中建立新的 PIN 原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8bdf0478-fe9f-4371-93ff-db39381a25db
description: '摘要: 在商務用 Skype Server 中建立新的 PIN 原則。'
ms.openlocfilehash: aaedcbfe28cb8e64b4adf7a302eef8c0d3d08a1f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189682"
---
# <a name="create-a-new-pin-policy-in-skype-for-business-server"></a>在商務用 Skype Server 中建立新的 PIN 原則
 
**摘要:** 在商務用 Skype Server 中建立新的 PIN 原則。
  
您可以使用 [**釘選原則**] 頁面, 為使用 IP 電話連線至商務用 Skype 的使用者提供個人識別碼 (pin) 驗證。 若要使用 PIN 驗證, 請確認已在 [Web 服務設定] 中選取 [**啟用 Pin 驗證**]。
  
請依照這些步驟來建立使用者層級或網站層級的 PIN 原則。 
  
### <a name="to-create-a-user-or-site-pin-policy"></a>建立使用者或網站 PIN 原則

1.  從屬於 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權利), 或指派給 CsServerAdministrator 或 CsAdministrator 角色, 登入您在其中部署商務用 Skype Server 的網路中的任何電腦.
    
2. 開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。 
    
3. 在左側導覽列中, 按一下 [**安全性**], 然後按一下 [ **PIN 規則**]。
    
4. 在 [ **PIN 原則**] 頁面上, 按一下 [**新增**], 然後執行下列其中一項操作:
    
   - 若要建立使用者層級原則, 按一下 [**使用者原則**]。 在 [**新 PIN 原則**] 的 [**名稱**] 中, 輸入描述原則的名稱。
    
   - 若要建立網站層級原則, 按一下 [**網站原則**]。 在 [**選取網站**搜尋] 欄位中, 輸入您要為其建立原則之網站的全部或部分名稱。 在產生的網站清單中, 按一下您想要的網站, 然後按一下 **[確定]**。
    
5. 在 [**描述**] 欄位中, 輸入 PIN 原則的描述。
    
6. 在 [**最小 pin 長度**] 欄位中, 輸入或選取您要允許的最小 PIN 長度。 預設的最小長度為5位數。
    
7. 若要在封鎖使用者之前, 能夠指定最大的登入嘗試次數, 請選取 [**指定最大登入嘗試**] 核取方塊。 如果您沒有選取此選項, 則會根據 PIN 長度自動判斷允許的最大嘗試次數上限。 根據預設, 會自動決定最大嘗試次數。
    
8. 如果您已選取 [**指定最大登入嘗試**] 核取方塊, 請在 [**最大登入次數**] 中, 輸入或選取您要允許的最大登入嘗試次數。
    
9. 若要讓 Pin 到期, 請選取 [**啟用 PIN 到期**日] 核取方塊。 如果您沒有選取此選項, 針腳將永不過期。 根據預設, Pin 永遠不會過期。
    
10. 如果您已選取 [**啟用 PIN 到期**日] 核取方塊, 請在 **[PIN 到期日之後 (天數)**] 中, 輸入或選取 pin 到期前的天數。
    
11. 在 [ **PIN 記錄計數**] 中, 輸入使用者必須建立才能重複使用 pin 的 pin 數。 根據預設, 使用者可以重複使用他們的 Pin。
    
12. 若要在 Pin 中允許常用位數模式 (例如 "1234" 和 "8888"), 請選取 [**允許一般模式**] 核取方塊。 如果您沒有選取此選項, 則只允許使用複雜的數位模式。 根據預設, 只允許使用複雜的數位模式。
    
    > [!IMPORTANT]
    > 我們建議您不要允許通用模式。 
  
13. 按一下 [認可]****。
    


---
title: 在商務用 Skype Server 中修改現有的 PIN 原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 517caaee-3349-4fa6-8d86-e4da3258a445
description: '摘要: 在商務用 Skype Server 中修改現有的 PIN 原則。'
ms.openlocfilehash: 9aecd7fc48ce2893e1d8e603f7cdc369cde11ec3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191569"
---
# <a name="modify-an-existing-pin-policy-in-skype-for-business-server"></a>在商務用 Skype Server 中修改現有的 PIN 原則
 
**摘要:** 在商務用 Skype Server 中修改現有的 PIN 原則。
  
您可以使用 [**釘選原則**] 索引標籤, 為使用 IP 電話連線至商務用 Skype 的使用者提供個人身分識別號碼 (PIN) 驗證。 若要使用 PIN 驗證, 請確認已在 [Web 服務設定] 中選取 [**啟用 Pin 驗證**]。
  
請依照這些步驟來修改使用者層級或網站層級的 PIN 原則。 
  
### <a name="to-modify-an-existing-pin-policy"></a>修改現有的 PIN 原則

1.  從屬於 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權利), 或指派給 CsServerAdministrator 或 CsAdministrator 角色, 登入您在其中部署商務用 Skype Server 的網路中的任何電腦.
    
2. 開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。 
    
3. 在左側導覽列中, 按一下 [**安全性**], 然後按一下 [ **PIN 規則**]。
    
4. 在 [ **PIN 原則**] 頁面上, 按一下原則, 按一下 [**編輯**], 然後按一下 [**顯示詳細資料**]。
    
5. 在 [**編輯 Pin 原則**] 的 [**最小 pin 長度**] 中, 輸入或選取您要允許的最小 pin 長度。 預設的最小長度為5位數。
    
6. 若要在封鎖使用者之前, 能夠指定最大的登入嘗試次數, 請選取 [**指定最大登入嘗試**] 核取方塊。 如果您沒有選取此選項, 則會根據 PIN 長度自動判斷允許的最大嘗試次數上限。 根據預設, 會自動決定最大嘗試次數。
    
7. 如果您已選取 [**指定最大登入嘗試**] 核取方塊, 請在 [**最大登入次數**] 中, 輸入或選取您要允許的最大登入嘗試次數。
    
8. 若要讓 Pin 到期, 請選取 [**啟用 PIN 到期**日] 核取方塊。 如果您沒有選取此選項, 針腳將永不過期。 根據預設, Pin 永遠不會過期。
    
9. 如果您已選取 [**啟用 PIN 到期**日] 核取方塊, 請在 **[PIN 到期日之後 (天數)**] 中, 輸入或選取 pin 到期前的天數。
    
10. 在 [ **PIN 記錄計數**] 中, 輸入使用者必須建立才能重複使用 pin 的 pin 數。 根據預設, 使用者可以重複使用他們的 Pin。
    
11. 若要在 Pin 中允許通用位數 (例如順序編號和重複的數位組), 請選取 [**允許常見模式**] 核取方塊。 如果您沒有選取此選項, 則只允許使用複雜的數位模式。 根據預設, 只允許使用複雜的數位模式。
    
    > [!IMPORTANT]
    > 我們建議您不要允許通用模式。 
  
12. 按一下 [認可]****。
    


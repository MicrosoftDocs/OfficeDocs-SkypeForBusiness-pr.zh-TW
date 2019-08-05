---
title: 在商務用 Skype 中建立或修改語音路線
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d189057d-cc9d-4622-9d10-f5385d703faf
description: '摘要: 瞭解如何使用商務用 Skype Server 控制台, 在商務用 Skype Server 中建立或修改語音路線。'
ms.openlocfilehash: f79e672b45f68e09391489da55023dceb3b0dd93
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190420"
---
# <a name="create-or-modify-a-voice-route-in-skype-for-business"></a>在商務用 Skype 中建立或修改語音路線
 
**摘要:** 瞭解如何使用商務用 Skype Server 控制台, 在商務用 Skype Server 中建立或修改語音路由。
  
### <a name="to-create-a-voice-route-by-using-the-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 的 [控制台] 建立語音路線

1. 以 RTCUniversalServerAdmins 群組的成員或**CsVoiceAdministrator**、 **CsServerAdministrator**或**CsAdministrator**系統管理角色的成員的身分登入電腦。
    
2. 開啟商務用 Skype Server 的 [控制台]。
    
3. 在左側導覽列中, 按一下 [**語音路由**]。
    
4. 按一下 [**傳送**]。
    
5. 按一下 [**新增**] 以顯示 [**新增語音路由**] 對話方塊。
    
6. 在 [**名稱**] 中, 輸入語音路線的描述性名稱。
    
7. 可選在 [**描述**] 中, 輸入語音路由的其他描述性資訊。
    
8. 若要指定您想要此路由適應的模式, 您可以使用 [**建立模式搭配**工具] 來產生正則運算式, 或是手動撰寫正則運算式。
    
   - 若要使用 [**建立模式以搭配**工具] 來產生正則運算式, 請輸入如下所示的值。 您可以指定兩種模式相符類型:
    
   - **您想要允許的數位起始位數**: 輸入此路由必須容納的 [首碼值] (包括前置 + 視需要)。 例如, 輸入 + 425, 然後按一下 [**新增**]。 針對您想要包含在路線中的每一個前置詞值, 重複此步驟。
    
   - **例外**狀況: 如果您想要指定一個或多個前置詞的例外狀況, 請醒目提示 [首碼], 然後按一下 [**例外**]。 針對您*不*想要此路線容納的相符模式, 輸入一或多個值。 例如, 若要從路由中排除從 + 425237 開始的數位, 請在 [**例外**] 欄位中輸入 [+ 425237] 的值, 然後按一下 **[確定]**。
    
   - 若要手動定義 [相符] 模式, 請按一下 [**組建符合**工具的模式] 中的 [**編輯**], 然後輸入 .net Framework 一般運算式, 以指定要套用路線之目的地電話號碼的相符模式。 如需如何撰寫正則運算式的詳細資料, 請參閱[".Net Framework 一般運算式"](https://go.microsoft.com/fwlink/p/?linkId=140927)。 
    
9. 如果您不想讓撥出通話的電話號碼出現在通話收件者, 請選取 [**取消來電**顯示]。 如果您選取此選項, 您必須指定將出現在收件者的本機號碼中的**替代呼叫者 id** 。
    
10. 若要將一或多個 trunks 與語音路線關聯, 請按一下 [**新增**], 然後從清單中選取主幹。
    
11. 若要將一或多個公開交換的電話網絡 (PSTN) 用法與語音路線關聯, 請按一下 [**選取**], 然後從已針對您的企業語音部署定義的 PSTN 使用狀況記錄清單中, 選擇一筆記錄。
    
    > [!NOTE]
    > 若要查看每個可用 PSTN 使用量記錄的屬性, 請參閱[在商務用 Skype 中查看 PSTN 使用狀況記錄](view-pstn-usage-records.md)。 > 若要建立或編輯 PSTN 使用記錄, 請參閱[在商務用 Skype 中建立或修改語音原則和設定 PSTN 使用記錄](voice-policy-and-pstn-usage-records.md)
  
12. 排列 PSTN 使用狀況記錄, 以獲得最佳效能。 若要變更記錄在清單中的位置, 請醒目提示記錄名稱, 然後按一下向上或向下箭號。
    
    > [!NOTE]
    > 與語音原則相反, 在其中列出 PSTN 使用記錄的順序非常重要, 而 PSTN 使用記錄在語音路由中所處的順序則是無意義的。 不過, 我們建議您依使用頻率來整理清單。 例如: RedmondLocal、RedmondLongDist、RedmondInternational、RedmondBackup。 (商務用 Skype Server 會從上方開始遍歷清單)。 
  
13. 可選在 [**輸入已翻譯的數位至測試**] 欄位中輸入值****, 然後按一下 [執行]。 測試結果會顯示在欄位下方。
    
14. 按一下 **[確定]** 儲存語音傳送。
    
    > [!IMPORTANT]
    > 每當您建立語音路線時, 您都必須執行 [**全部提交**] 命令來發佈設定變更。 如需詳細資訊, 請參閱[在商務用 Skype 中發佈待處理的語音路由設定變更](voice-route-config-changes.md)。 
  
### <a name="to-modify-a-voice-route"></a>修改語音路線

1. 開啟商務用 Skype Server 的 [控制台]。
    
2. 在左側導覽列中, 按一下 [**語音路由**], 然後按一下 [**傳送**]。
    
3. 在 [**工藝路線**] 頁面上, 使用下列其中一種方法來修改語音路線:
    
   - 按一下語音路由名稱, 按一下 [**編輯**], 然後按一下 [**顯示詳細資料**]。
    
   - 按一下語音路由名稱, 按一下 [**編輯**], 按一下 [**複製**], 然後按一下 [**貼**上]。 按一下您剛建立的語音信箱新複本, 按一下 [**編輯**], 然後按一下 [**顯示詳細資料**]。
    
4. 在 [**編輯語音路線**] 頁面上的 [**名稱**] 欄位中, 輸入語音路線的描述性名稱。
    
5. 可選在 [**描述**] 欄位中, 輸入語音路線的其他描述性資訊。
    
6. 若要指定您想要此路由容納的模式, 您可以使用 [**建立模式搭配**工具] 來產生正則運算式, 或是手動撰寫正則運算式。
    
   - 若要使用 [**建立模式以搭配**工具] 來產生正則運算式, 請輸入如下所示的值。 您可以指定兩種模式相符類型:
    
   - **您想要允許的數位起始位數**: 輸入此路由必須容納的 [首碼值] (包括前置 + 視需要)。 例如, 輸入 + 425, 然後按一下 [**新增**]。 針對您想要包含在路線中的每一個前置詞值, 重複此步驟。
    
   - **例外**狀況: 如果您想要指定一個或多個前置詞的例外狀況, 請醒目提示 [首碼], 然後按一下 [**例外**]。 針對您*不*想要此路線容納的相符模式, 輸入一或多個值。 例如, 若要從路由中排除從 + 425237 開始的數位, 請在 [**例外**] 欄位中輸入 [+ 425237] 的值, 然後按一下 **[確定]**。
    
   - 若要手動定義 [相符] 模式, 請按一下 [**組建符合**工具的模式] 中的 [**編輯**], 然後輸入 .net Framework 一般運算式, 以指定要套用路線之目的地電話號碼的相符模式。如需如何撰寫正則運算式的詳細資料, 請參閱[".Net Framework 一般運算式"](https://go.microsoft.com/fwlink/p/?linkId=140927)。 
    
7. 如果您不想讓撥出通話的電話號碼出現在通話收件者, 請選取 [**取消來電**顯示]。 如果您選取此選項, 您必須指定將出現在收件者的本機號碼中的**替代呼叫者 id** 。
    
8. 若要將一或多個公開交換的電話網絡 (PSTN) trunks 與語音路線關聯, 請按一下 [**新增**], 然後從清單中選取主幹。
    
9. 若要將一或多個 PSTN 使用方式與語音路由建立關聯, 請按一下 [**選取**], 然後從針對您的企業語音部署定義的 PSTN 使用狀況記錄清單中選擇記錄。
    
    > [!NOTE]
    > 若要查看每個可用 PSTN 使用量記錄的屬性, 請參閱[在商務用 Skype 中查看 PSTN 使用狀況記錄](view-pstn-usage-records.md)。 > 若要建立或編輯 PSTN 使用記錄, 請參閱[在商務用 Skype 中建立或修改語音原則和設定 PSTN 使用記錄](voice-policy-and-pstn-usage-records.md)。 
  
10. 排列 PSTN 使用狀況記錄, 以獲得最佳效能。 若要變更記錄在清單中的位置, 請醒目提示記錄名稱, 然後按一下向上或向下箭號。
    
    > [!NOTE]
    > 相對於語音原則, 其中列出 PSTN 使用記錄的順序非常重要, 因此語音路由中的 PSTN 使用記錄順序不是多餘的。 不過, 我們建議您依使用頻率來組織清單, 例如: RedmondLocal、RedmondLongDist、RedmondInternational、RedmondBackup。 (商務用 Skype Server 會從上方開始遍歷清單)。 
  
11. 可選在 [**輸入已翻譯的數位至測試**] 欄位中輸入值****, 然後按一下 [執行]。 測試結果會顯示在欄位下方。
    
12. 按一下 [確定]****。
    
13. 在 [**路由**] 頁面上, 按一下 [**認可**], 然後按一下 [**全部提交**]。 
    
    > [!NOTE]
    > 每當您建立或修改語音路線時, 您都必須執行 [**全部提交**] 命令才能發佈設定變更。 如需詳細資訊, 請參閱在作業檔中[發佈商務用 Skype 中的語音路由設定的待處理變更](voice-route-config-changes.md)。
  
## <a name="see-also"></a>另請參閱

[在商務用 Skype 中查看 PSTN 使用狀況記錄](view-pstn-usage-records.md)
  
[在商務用 Skype 中建立或修改語音原則及設定 PSTN 使用記錄](voice-policy-and-pstn-usage-records.md)
  
[在商務用 Skype 中發佈 [語音路由設定] 的擱置變更](voice-route-config-changes.md)


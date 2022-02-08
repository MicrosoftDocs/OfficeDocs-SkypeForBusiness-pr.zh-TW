---
title: 在商務用 Skype 中建立或修改語音路由
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d189057d-cc9d-4622-9d10-f5385d703faf
description: 摘要：瞭解如何使用商務用 Skype Server 控制台，在商務用 Skype Server 中建立或修改語音路由。
ms.openlocfilehash: ec890cdbb9f1e05463d5957ac6e8cae95dac3d51
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62390705"
---
# <a name="create-or-modify-a-voice-route-in-skype-for-business"></a>在商務用 Skype 中建立或修改語音路由
 
**總結：** 瞭解如何使用商務用 Skype Server 控制台，在商務用 Skype Server 中建立或修改語音路由。
  
### <a name="to-create-a-voice-route-by-using-the-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 控制台建立語音路由

1. 以 RTCUniversalServerAdmins 群組成員的身分，或是 **CsVoiceAdministrator**、 **CsServerAdministrator** 或 **CsAdministrator** 系統管理角色的成員身分登入電腦。
    
2. 開啟商務用 Skype Server 控制台]。
    
3. 在左導覽列中，按一下 **[語音路由]**。
    
4. 按一下 **[路由]**。
    
5. 按一下 [ **新增** ] 顯示 [ **新增語音路由** ] 對話方塊。
    
6. 在 [ **名稱**] 中，輸入語音路由的描述性名稱。
    
7.  (選用) 在 [ **描述**] 中，輸入語音路由的其他描述性資訊。
    
8. 若要指定您想要此路由容納的模式，您可以使用 **Build a pattern to match** tool 以產生正則運算式，或是手動寫入正則運算式。
    
   - 若要使用 **Build a pattern to match** tool 以產生正則運算式，請輸入下列的值。 您可以指定兩種類型的模式對應：
    
   - **您想要允許的數位的開始位數**：輸入此路由必須滿足的首碼值 (包括前置 + （如果需要）) 。 例如，輸入 + 425，然後按一下 [ **新增**]。 針對您想要包含在路由中的每個前置詞值，重複此步驟。
    
   - **例外** 狀況：如果您想要為前置詞值指定一或多個例外狀況，請反白顯示首碼，然後按一下 [ **例外** 狀況]。 針對您  *不*  想要此路由容納的相符模式輸入一個或多個值。 例如，若要從路由中排除從 + 425237 開始的數位，請在 [ **例外日期** ] 欄位中輸入 [+ 425237] 的值，然後按一下 **[確定]**。
    
   - 若要手動定義相符的模式，請按一下 [**組建要搭配的模式**] 中的 [**編輯**]，然後輸入 .NET Framework 正則運算式，指定要套用路由之目的地電話號碼的相符模式。 如需如何撰寫正則運算式的詳細資訊，請參閱「 [.NET Framework 正則運算式](/dotnet/standard/base-types/regular-expressions)」。 
    
9. 如果您不想讓撥出電話的電話號碼對來電收件者顯示，請選取 [ **抑制來電者識別碼** ]。 如果您選取此選項，則必須指定要在收件者的來電者 ID 顯示上顯示的 **替代來電者識別碼** 。
    
10. 若要將一或多個主幹與語音路由產生關聯，請按一下 [ **新增** ]，然後從清單中選取一個主幹。
    
11. 若要將一或多個公用交換電話網路 (PSTN) 使用方式與語音路由產生關聯，請按一下 [**選取**]，然後從為您的企業語音部署定義的 PSTN 使用方式記錄清單中，選擇記錄。
    
    > [!NOTE]
    > 若要查看每個可用的 PSTN 使用方式記錄的屬性，請參閱[在商務用 Skype 中查看 PSTN 使用方式記錄](view-pstn-usage-records.md)。 > 若要建立或編輯 PSTN 使用方式記錄，請參閱[在商務用 Skype 中建立或修改語音原則及設定 pstn 使用方式記錄](voice-policy-and-pstn-usage-records.md)
  
12. 排列 PSTN 使用方式記錄，以獲得最佳效能。 若要變更記錄在清單中的位置，請反白顯示記錄名稱，然後按一下向上或向下箭號。
    
    > [!NOTE]
    > 與語音原則不同的是，列出 PSTN 使用方式記錄的順序很重要，因此語音路由中列出 PSTN 使用方式記錄的順序是沒有意義的。 不過，我們建議您依使用頻率來組織清單。 例如： RedmondLocal、RedmondLongDist、RedmondInternational、RedmondBackup。  (商務用 Skype Server 從上向中從上向上遍歷清單。 )  
  
13.  (選用) 在 [ **輸入要測試的轉譯的號碼** ] 欄位中輸入值，然後按一下 [ **移至**]。 測試結果會顯示在欄位底下。
    
14. 按一下 **[確定]** 以儲存語音路由。
    
    > [!IMPORTANT]
    > 每當您建立語音路由時，都必須執行「 **認可全部** 」命令來發佈設定變更。 如需詳細資訊，請參閱[在商務用 Skype 中發佈擱置的變更至語音路由](voice-route-config-changes.md)設定。 
  
### <a name="to-modify-a-voice-route"></a>修改語音路由

1. 開啟商務用 Skype Server 控制台]。
    
2. 在左導覽列中，按一下 [ **語音路由**]，然後按一下 [ **路由**]。
    
3. 在 [ **路由** ] 頁面上，使用下列其中一種方法來修改語音路由：
    
   - 按一下 voice route 名稱，按一下 [ **編輯**]，然後按一下 [ **顯示詳細資料**]。
    
   - 依序按一下 voice route 名稱、[ **編輯**] 和 [ **複製**]，然後按一下 [ **貼** 上]。 按一下您剛建立之語音路由的新複本，按一下 [ **編輯**]，然後按一下 [ **顯示詳細資料**]。
    
4. 在 [**編輯語音路由**] 頁面上的 [**名稱**] 欄位中，輸入語音路由的描述性名稱。
    
5.  (選用) 在 [ **描述** ] 欄位中，輸入語音路由的其他描述性資訊。
    
6. 若要指定您想要此路由容納的模式，您可以使用 **Build a pattern to match** tool 以產生正則運算式，或是手動寫入正則運算式。
    
   - 若要使用 **Build a pattern to match** tool 以產生正則運算式，請輸入下列的值。 您可以指定兩種類型的模式對應：
    
   - **您想要允許的數位的開始位數**：輸入此路由必須滿足的首碼值 (包括前置 + （如果需要）) 。 例如，輸入 + 425，然後按一下 [ **新增**]。 針對您想要包含在路由中的每個前置詞值，重複此步驟。
    
   - **例外** 狀況：如果您想要為前置詞值指定一或多個例外狀況，請反白顯示首碼，然後按一下 [ **例外** 狀況]。 針對您  *不*  想要此路由容納的相符模式輸入一個或多個值。 例如，若要從路由中排除從 + 425237 開始的數位，請在 [ **例外日期** ] 欄位中輸入 [+ 425237] 的值，然後按一下 **[確定]**。
    
   - 若要手動定義相符的模式，請按一下 [**組建要搭配的模式**] 中的 [**編輯**]，然後輸入 .NET Framework 正則運算式，指定要套用路由之目的地電話號碼的相符模式。如需如何撰寫正則運算式的詳細資訊，請參閱「 [.NET Framework 正則運算式](/dotnet/standard/base-types/regular-expressions)」。 
    
7. 如果您不想讓撥出呼叫出現在來電收件者的電話識別碼，請選取 [ **抑制來電者識別碼** ]。 如果您選取此選項，則必須指定要在收件者的來電者 ID 顯示上顯示的 **替代來電者識別碼** 。
    
8. 若要將一或多個公用交換電話網路 (PSTN) 主幹與語音路由產生關聯，請按一下 [ **新增**]，然後從清單中選取一個主幹。
    
9. 若要將一或多個 PSTN 使用方式與語音路由產生關聯，請按一下 [**選取**]，然後從為您的企業語音部署定義的 PSTN 使用方式記錄清單中，選擇記錄。
    
    > [!NOTE]
    > 若要查看每個可用的 PSTN 使用方式記錄的屬性，請參閱[在商務用 Skype 中查看 PSTN 使用方式記錄](view-pstn-usage-records.md)。 > 若要建立或編輯 PSTN 使用方式記錄，請參閱[建立或修改語音原則和設定商務用 Skype 中的 PSTN 使用方式記錄](voice-policy-and-pstn-usage-records.md)。 
  
10. 排列 PSTN 使用方式記錄，以獲得最佳效能。 若要變更記錄在清單中的位置，請反白顯示記錄名稱，然後按一下向上或向下箭號。
    
    > [!NOTE]
    > 相對於語音原則，其中列出 PSTN 使用方式記錄的順序很重要，語音路由中的 PSTN 使用方式記錄的順序是無關緊要的。 不過，我們建議您依使用頻率來組織清單，例如： RedmondLocal、RedmondLongDist、RedmondInternational、RedmondBackup。  (商務用 Skype Server 從上向中從上向上遍歷清單。 )  
  
11.  (選用) 在 [ **輸入要測試的轉譯的號碼** ] 欄位中輸入值，然後按一下 [ **移至**]。 測試結果會顯示在欄位底下。
    
12. 按一下 [確定]。
    
13. 在 [ **路由** ] 頁面上，按一下 [ **認可**]，然後按一下 [ **全部認可**]。 
    
    > [!NOTE]
    > 當您建立或修改語音路由時，您必須執行「 **認可全部** 」命令來發佈設定變更。 如需詳細資訊，請參閱操作檔中的[商務用 Skype 發佈擱置變更至語音路由](voice-route-config-changes.md)設定。
  
## <a name="see-also"></a>另請參閱

[在商務用 Skype 中查看 PSTN 使用方式記錄](view-pstn-usage-records.md)
  
[在商務用 Skype 中建立或修改語音原則及設定 PSTN 使用方式記錄](voice-policy-and-pstn-usage-records.md)
  
[在商務用 Skype 中發佈語音路由設定的擱置變更](voice-route-config-changes.md)
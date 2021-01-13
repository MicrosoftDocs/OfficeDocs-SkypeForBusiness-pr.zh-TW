---
title: 在商務用 Skype Server 2015 中開始或停止 CLS 記錄捕獲
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
description: 摘要：瞭解如何在商務用 Skype Server 2015 中啟動或停止集中式記錄服務記錄捕獲會話。
ms.openlocfilehash: cd6864b0d4d16e952f93fe321b49522028d76e5b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835133"
---
# <a name="start-or-stop-cls-log-capture-in-skype-for-business-server-2015"></a>在商務用 Skype Server 2015 中開始或停止 CLS 記錄捕獲
 
**摘要：** 瞭解如何在商務用 Skype Server 2015 中啟動或停止集中式記錄服務記錄捕獲會話。
  
若要使用集中式記錄服務來捕獲追蹤記錄檔，您會發出命令，以開始登入一或多部電腦及集區。 您也可以發出參數，定義哪些電腦或集區、要執行哪些案例 (例如，AlwaysOn、其他預先定義的案例或您已建立的案例) ， (的商務用 Skype Server 元件例如，S4，SipStack) 來追蹤。
  
為了擷取正確的資訊，您必須確定使用正確的案例來收集問題的相關資訊。 在集中式記錄服務中，案例是指根據伺服器元件的集合、記錄層級和旗標來開啟記錄的概念，其效率更高，而且在每個伺服器基礎上都必須定義這些元素時非常實用。 您可以定義及指定要執行的案例，這些案例會在基礎結構範圍內的所有伺服器和集區上持續執行。
  
預設案例稱為 **AlwaysOn**。AlwaysOn 的預定目的是持續執行案例 (如案例名稱所指)。AlwaysOn 案例針對許多最常見的伺服器元件，收集資訊層級的資訊 (請注意，資訊記錄層次除了資訊訊息之外，還包含 [嚴重]、[錯誤] 及 [警告])。AlwaysOn 會收集發生問題前後及期間的資訊。這與之前的記錄工具 (例如 OCSLogger) 的一般行為大不相同。您會在發生問題之後執行 OCSLogger，這讓疑難排解工作更加困難，因為您擁有的資料只會被動回應，而無法主動解決問題。如果 AlwaysOn 所包含的資訊，不是您想要指向問題元件及指出修正步驟的資訊 (在 AlwaysOn 提供者的深度和廣度下，此情形並不常見)，AlwaysOn 會指出合理的資訊層級，以決定必須執行的其他動作，例如建立新的案例、收集其他資訊、執行其他搜尋以收集更集中的詳細資料等。
  
集中式記錄服務提供兩種方式發出命令。 許多主題透過商務用 Skype Server 管理命令介面，以 Windows PowerShell 為重點 squarely。 使用許多複雜設定和命令的能力，可對 Windows PowerShell 以進行集中式記錄服務使用。 由於 Windows PowerShell 透過商務用 Skype Server 管理命令介面幾乎到處是商務用 Skype Server 中的所有功能，因此只討論 Windows PowerShell 命令。 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a>使用基本命令以 Windows PowerShell 執行 Start-CsClsLogging

1. 啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。
    
2. 輸入下列命令，以集中式記錄服務開機記錄案例：
    
   ```PowerShell
   Start-CsClsLogging -Scenario <name of scenario>
   ```

    例如，若要啟動 **AlwaysOn** 案例，請輸入：
    
   ```PowerShell
   Start-CsClsLogging -Scenario AlwaysOn
   ```

    > [!NOTE]
    > AlwaysOn 案例沒有預設期間。 此案例會一直執行，直到您使用 **Stop-CsClsLogging** Cmdlet 明確加以停止。 如需詳細資訊，請參閱＜[Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps)＞。 其他所有案例的預設期間為 4 小時。 
  
3. 按 Enter 鍵執行命令。 
    
    > [!NOTE]
    > 可能需要一點時間 (30 到 60 秒) 才能執行命令，並接收部署中的電腦傳回的狀態。 
  
     ![執行 Start-CsClsLogging。](../../media/Ops_CLS_Show_and_Start_ClsLogging.jpg)
  
4. 若要開始另一種情況，請使用 **Start-CsClsLogging** Cmdlet 及其他案例的名稱來執行，如下所示 (例如，案例 **驗證**) ：
    
   ```PowerShell
   Start-CsClsLogging -Scenario Authentication
   ```

    > [!IMPORTANT]
    > 在任何時候，最多可以在任何指定的電腦上執行兩個案例。 如果命令的範圍為全域，部署中的所有電腦都會執行這些案例。 若要啟動第三個案例，您必須從要執行新案例的電腦、集區、網站或全域範圍停止記錄。 如果已啟動全域範圍，您可以在一或多部電腦和集區上停止記錄一或兩個案例。 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a>使用 Windows PowerShell 使用 advanced 命令執行 Start-CsClsLogging

1. 啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。
    
2. 您可以使用其他參數管理記錄命令。 您可以使用-Duration 來調整案例的執行時間長度。 您也可以定義電腦、電腦完整功能變數名稱的清單 (Fqdn) 以逗號分隔的集區清單，以逗號分隔，以供您要執行記錄的集區的 Fqdn。
    
    您為集區 "pool01.contoso.net" 上的 UserReplicator 案例開始記錄會話。 您也可以將記錄工作階段期間定義為 8 小時。 若要執行這項操作，請輸入：
    
   ```PowerShell
   Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
   ```

    成功執行此案例會傳回類似如下的結果：
    
     ![執行 Start-CsClsLogging。](../../media/Ops_CsClsLogging_UserReplicator_Exp.jpg)
  
請注意，在此範例中，AlwaysOn 案例和 UserReplicator 案例都在執行中。 
    
## <a name="stop-the-centralized-logging-service-log-capture"></a>停止集中式記錄服務記錄捕獲
<a name="stop"> </a>

您可以用 Stop-CsClsLogging Cmdlet 來停止目前執行中的記錄工作階段。 一般來說，在許多情況下，您不需要停止記錄會話。 例如，您不需要先停止記錄，就可以搜尋記錄及變更設定。 如果您有兩個案例正在執行，例如 AlwaysOn 和 UserReplicator，而您需要收集有關驗證的資訊，則必須先停止其中一個案例 (在全域、網站、集區或電腦範圍)，才能開始執行驗證案例。 如需詳細資訊，請參閱＜[Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps)＞。
  
> [!NOTE]
> 在決定您可以在指定的部署、集區或電腦上執行哪些案例時，您必須記得 **每台電腦** 都限制執行兩個案例： AlwaysOn 和一個自訂案例。 如果您要在集區上記錄活動，則應將集區當做單一實體來處理。 在大部分情況下，在集區中的每部電腦上執行不同的案例並沒有意義。 但是查看您收集資料的相關問題，並思考在整體部署中，哪個案例對給定電腦的影響最大，這就有意義了。 例如，如果您考慮 UserReplicator 案例，在 Edge Server 或 Edge 集區上執行 UserReplicator 時，會有很小的價值。 
  
在了解問題及影響的範圍之後，應謹慎選擇要在哪些電腦和集區上執行什麼案例。雖然 AlwaysOn 案例對大範圍的應用有意義，因為它會收集各種提供者的資訊，但是特定案例對特定電腦或集區只有應用價值。此外，在未了解給定案例的價值之前，就隨機啟動記錄工作階段的話，要特別小心。如果您使用錯誤的案例，或是所使用的案例適合該工作，而您將案例套用在錯誤的範圍 (可能是全域、網站、集區或電腦)，所得到的問題資料可能不是很有用，就像根本沒有執行案例一樣。
  
若要使用商務用 Skype Server 管理命令介面來控制集中式記錄服務功能，您必須是 CsAdministrator 或 CsServerAdministrator 角色型存取控制 (RBAC) 安全性群組的成員，或是包含這兩個群組之任一個自訂 RBAC 角色的成員。 若要傳回所有獲指派此 Cmdlet 的 RBAC 角色清單 (包含您自行建立的自訂 RBAC 角色) ，請從商務用 Skype Server 管理命令介面或 Windows PowerShell 提示中執行下列命令：
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

例如：
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> 您可能會想知道：現在已經啟用記錄，記錄檔會保留在何處？ 由於您將使用傳送至 CLS 代理程式的管理命令介面查詢，存取儲存在記錄檔中的資訊，因此您可以將結果輸出成幾種可能的檔案格式，在每一部伺服器上，CLS 代理程式都可以保留其記錄，但實際上並無重要的瞭解。  您可以使用各種工具（包括Snooper.exe及可讀取文字檔的任何工具）將記錄檔儲存至您指定的位置，包括和任何可讀取文字檔的工具，例如 **Notepad.exe**。 Snooper.exe 是商務用 Skype Server 2015 調試工具的一部分，可供 [網頁下載](https://go.microsoft.com/fwlink/p/?LinkId=285257)使用。

### <a name="to-stop-a-currently-running-centralized-logging-service-session"></a>停止目前執行中的集中式記錄服務會話

1. 啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。
    
2. 輸入下列命令來查詢集中式記錄服務，以找出目前正在執行的案例：
    
   ```PowerShell
   Show-CsClsLogging
   ```

   ![呼叫 Show-CsCl 後的 Windows PowerShell 主控台](../../media/Ops_Show_Stop_CsClsLogging.jpg)
  
   Show-CsClsLogging 的結果是執行中案例及其執行範圍的摘要。 如需詳細資訊，請參閱＜[Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps)＞。
    
3. 若要停止使用特定案例的目前執行中記錄工作階段，請輸入：
    
   ```PowerShell
   Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
   ```
   例如：
    
   ```PowerShell
   Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
   ```

   此命令將會停止 pool01.contoso.net 上使用 UserReplicatior 案例的記錄。
    
    > [!NOTE]
    > 在此記錄工作階段期間，使用 UserReplicator 案例來建立的記錄並不會刪除。 您還是可以使用該記錄來執行使用 Search-CsClsLogging 命令的搜尋作業。 如需詳細資訊，請參閱＜[Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps)＞。 
  
Stop-CsClsLogging Cmdlet 與 Start-CsClsLogging 搭配使用時，會結束記錄工作階段 (由案例定義)，並保留記錄工作階段所建立的記錄。您隨時都可以在給定的電腦上執行兩個案例。用一個案例停止另一個案例來收集資訊的方法，是在大部分工作量疑難排解期間都可以執行的常用工作。
## <a name="see-also"></a>另請參閱
<a name="stop"> </a>

[商務用 Skype 2015 中的集中式記錄服務](centralized-logging-service.md)

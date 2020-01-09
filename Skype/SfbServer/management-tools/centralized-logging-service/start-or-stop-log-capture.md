---
title: 開始或停止商務用 Skype 2015 中的 CLS 記錄擷取
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
description: 摘要：瞭解如何在商務用 Skype Server 2015 中啟動或停止集中式記錄服務記錄捕獲會話。
ms.openlocfilehash: b4da74e05a1eb6f6945f44c0c045c2292e7acca7
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991438"
---
# <a name="start-or-stop-cls-log-capture-in-skype-for-business-server-2015"></a>開始或停止商務用 Skype 2015 中的 CLS 記錄擷取
 
**摘要：** 瞭解如何在商務用 Skype Server 2015 中啟動或停止集中式記錄服務記錄捕獲會話。
  
若要使用集中式記錄服務來捕獲追蹤記錄，您需要發出命令，以便在一或多部電腦和池上開始記錄。 您也可以發出可定義哪些電腦或池、要執行的案例（例如，AlwaysOn、另一個預先定義的案例或您所建立的案例）的參數，以及要追蹤的商務用 Skype Server 元件（例如，S4、SipStack）。
  
若要捕獲正確的資訊，您必須確認使用正確的案例，才能收集與問題相關的資訊。 在集中式記錄服務中，案例是根據伺服器元件集合、記錄層級和旗標來開啟記錄的概念，這比要在每個伺服器上定義這些元素更有效率且更有用。 您定義並指定要執行的案例，並在整個基礎結構範圍中的所有伺服器和池上一致地執行該案例。
  
預設案例稱為 [ **AlwaysOn**]。 AlwaysOn 的預期用途是經常執行該案例，因為案例的名稱所隱含。 AlwaysOn 案例會收集資訊層級資訊（請注意，資訊記錄層級除了資訊訊息之外，還包含許多最常見伺服器元件的致命、錯誤和警告）。 AlwaysOn 會在問題發生之前、期間及之後收集資訊。 這與前一筆記錄工具（例如 OCSLogger）的一般行為有顯著的差異。 您在問題發生之後執行了 OCSLogger，因為您所擁有的資料是被動而非主動，所以您的疑難排解工作變得更困難。 如果 AlwaysOn 不包含您要尋找的資訊，而是要指向問題元件，並指出一個動作程式來修正它（不太可能是在 AlwaysOn 中提供提供者的廣度與深度），它會指出適當的資訊層級rmation 以判斷您需要執行的其他動作，例如建立新案例、收集其他資訊、執行不同的搜尋，以收集更專注的詳細資料等等。
  
集中式記錄服務提供兩種方式來發出命令。 您可以透過商務用 Skype Server Management 命令介面，在 Windows PowerShell 中，有許多主題是焦點恰好。 使用許多複雜的設定和命令的能力，有利於使用 Windows PowerShell 來集中式記錄服務。 因為 Windows PowerShell 透過商務用 Skype Server 管理命令介面幾乎無處不在商務用 Skype Server 中的所有功能，所以只討論 Windows PowerShell 命令。 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a>使用基本命令在 Windows PowerShell 中執行開始 CsClsLogging

1. 啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。
    
2. 輸入以下內容，以集中式記錄服務開機記錄案例：
    
   ```PowerShell
   Start-CsClsLogging -Scenario <name of scenario>
   ```

    例如，若要啟動**AlwaysOn**案例，請輸入：
    
   ```PowerShell
   Start-CsClsLogging -Scenario AlwaysOn
   ```

    > [!NOTE]
    > AlwaysOn 案例沒有預設的持續時間。 這個案例將會在您明確地停止使用**CsClsLogging** Cmdlet 之前執行。 如需詳細資訊，請參閱[停止 CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps)。 在所有其他案例中，預設期間是4小時。 
  
3. 按 Enter 以執行命令。 
    
    > [!NOTE]
    > 您可能需要花很短的時間（30到60秒），才能執行這些命令，並從您的部署中的電腦接收傳回的狀態。 
  
     ![執行 Start-CsClsLogging。](../../media/Ops_CLS_Show_and_Start_ClsLogging.jpg)
  
4. 若要開始其他案例，請使用**CsClsLogging** Cmdlet 及其他案例的名稱來執行，如下所示（例如，案例**驗證**）：
    
   ```PowerShell
   Start-CsClsLogging -Scenario Authentication
   ```

    > [!IMPORTANT]
    > 您可以隨時在任何指定電腦上執行兩種情況。 如果命令是全域在範圍中，則您部署中的所有電腦都會執行案例或案例。 若要開始第三個案例，您必須停止記錄您想要在其上執行新案例的電腦、池、網站或全域範圍。 如果您已開始全域範圍，您可以在一或多部電腦和池上停止記錄一或兩個案例的記錄。 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a>使用 [高級命令] 在 Windows PowerShell 中執行開始 CsClsLogging

1. 啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。
    
2. 還有其他參數可供您記錄管理命令。 您可以使用 [持續時間] 來調整案例執行的時間長度。 您也可以定義電腦（一份電腦完整功能變數名稱（Fqdn），由逗號或池分隔，您想要執行記錄的池以逗號分隔的 Fqdn 清單。
    
    您在「pool01.contoso.net」的 [UserReplicator] 案例中開機記錄會話。 您也可以在8小時定義記錄會話的持續時間。 若要這樣做，請輸入：
    
   ```PowerShell
   Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
   ```

    這個案例的成功執行會傳回如下所示的結果：
    
     ![執行 Start-CsClsLogging。](../../media/Ops_CsClsLogging_UserReplicator_Exp.jpg)
  
請注意，在這個範例中，AlwaysOn 案例正在執行，且 UserReplicator 案例正在執行。 
    
## <a name="stop-the-centralized-logging-service-log-capture"></a>停止集中式記錄服務記錄捕獲
<a name="stop"> </a>

您可以停止目前正在執行的記錄會話與 CsClsLogging Cmdlet。 一般來說，在許多情況下，您不需要停止記錄會話。 例如，您可以搜尋記錄並變更配置，而不需要先停止記錄。 如果您有兩種情況（例如，AlwaysOn 和 UserReplicator），而您需要收集驗證的相關資訊，您必須先停止其他案例（全域、網站、池或電腦範圍），才能開始執行到驗證案例。 如需詳細資訊，請參閱[停止 CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps)。
  
> [!NOTE]
> 在決定您可以在指定的部署、池或電腦上執行哪些案例時，您必須記住，**每個電腦**只能執行兩個案例： AlwaysOn 與一個自訂案例。 如果您要記錄池中的活動，您應該將一個池視為單一實體。 在大部分的情況下，在池中的每個電腦上執行不同的案例不是很有意義的。 您可以在收集資料時查看問題，並思考在整個部署中的指定電腦上最有意義的案例，這是很有説明的。 例如，如果您認為 UserReplicator 案例，在 Edge 伺服器或 Edge 池中執行 UserReplicator 時，會有非常小的值。 
  
在您瞭解問題及影響範圍之後，您應該謹慎選擇要在哪些電腦和池中執行哪些案例。 雖然 AlwaysOn 作用中的應用程式會在各種提供者上收集資訊，但 AlwaysOn 情況是有意義的，因為它會在特定的電腦或池中只有應用程式值。 此外，您也應該小心地開機記錄會話，而不需要先瞭解特定案例的價值。 如果您使用的是錯誤的案例，或是您使用適合工作的案例，且您在錯誤的範圍（全域、網站、池或電腦）中套用案例，您就可以取得可疑的資料，這並不是很實用的，就像您沒有執行該案例一樣。
  
若要使用商務用 Skype Server Management 命令介面控制集中式記錄服務的功能，您必須是 CsAdministrator 或 CsServerAdministrator 角色的存取控制（RBAC）安全性群組的成員，或是自訂的 RBAC 角色包含這兩個群組的其中一個。 若要傳回已指派這個 Cmdlet 的所有 RBAC 角色清單（包括您自行建立的任何自訂 RBAC 角色），請從商務用 Skype Server 管理命令介面或 Windows PowerShell 提示中執行下列命令：
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

例如：
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> 您可能會想知道：現在您已啟用記錄功能，這些記錄會保留在哪裡？ 由於您將使用傳送至 CLS 代理程式的管理命令介面查詢來存取儲存在記錄中的資訊，因此您可以將結果輸出為幾種可能的檔案格式，而在每個伺服器上，CLS 代理程式都能讓其記錄保持不太重要的意義。  記錄檔可以儲存在您指定的位置，並使用各種不同的工具讀取及分析，包括**Snooper**及任何可讀取文字檔（例如**notepad.exe**）的工具。 Snooper 是商務用 Skype Server 2015 調試工具的一部分，可在[網頁版下載](https://go.microsoft.com/fwlink/p/?LinkId=285257)中取得。

### <a name="to-stop-a-currently-running-centralized-logging-service-session"></a>停止目前正在執行的集中式記錄服務會話

1. 啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。
    
2. 在集中式記錄服務中輸入下列命令，以查詢目前正在執行的案例：
    
   ```PowerShell
   Show-CsClsLogging
   ```

   ![呼叫 Show-CsCl 之後的 Windows PowerShell 主控台](../../media/Ops_Show_Stop_CsClsLogging.jpg)
  
   CsClsLogging 的結果就是執行中之案例的摘要，以及它們正在執行的範圍。 如需詳細資訊，請參閱[顯示-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps)。
    
3. 若要停止目前正在執行的記錄會話與特定案例，請輸入：
    
   ```PowerShell
   Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
   ```
   例如：
    
   ```PowerShell
   Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
   ```

   這個命令會在 pool01.contoso.net 上停止記錄 UserReplicatior 案例。
    
    > [!NOTE]
    > 使用 UserReplicator 案例在這個記錄會話期間建立的記錄不會被刪除。 您仍可使用 [搜尋-CsClsLogging] 命令來執行搜尋的記錄。 如需詳細資訊，請參閱[搜尋-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps)。 
  
作為開始 CsClsLogging 的操作命令，Stop CsClsLogging Cmdlet 會結束記錄會話，由案例定義，並保留記錄會話所建立的記錄。 您可以隨時在指定的電腦上執行兩種案例。 停止某個案例以使用其他案例收集資訊的方法，是您可以在大部分工作負載疑難排解期間執行的一般工作。
## <a name="see-also"></a>另請參閱
<a name="stop"> </a>

[商務用 Skype 2015 中的集中式記錄服務](centralized-logging-service.md)

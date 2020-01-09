---
title: 管理商務用 Skype 2015 中集中式記錄服務組態設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
description: 摘要：瞭解如何在商務用 Skype Server 2015 中針對集中式記錄服務，進行檢索、更新及建立配置設定。
ms.openlocfilehash: 20f62a5568bef6f11eab35e13fa4e4f7adf8102e
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991458"
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a>管理商務用 Skype 2015 中集中式記錄服務組態設定

**摘要：** 瞭解如何在商務用 Skype Server 2015 中針對集中式記錄服務，進行檢索、更新及建立配置設定。

集中式記錄服務由集中式記錄服務控制器（CLSController）所建立和使用的設定和參數加以控制和設定，以便將命令傳送到個別電腦的集中式記錄服務代理程式（CLSAgent). Agent 會處理傳送給它的命令，（在 [開始] 命令中）會使用案例、提供者、追蹤持續時間及旗標的設定來開始根據所提供的配置資訊來收集追蹤記錄。

> [!IMPORTANT]
>  並非所有針對集中式記錄服務列出的 Windows PowerShell Cmdlet 都適用于商務用 Skype Server 2015 內部部署。 雖然這些程式可能看起來正常運作，但下列 Cmdlet 並非設計為與商務用 Skype Server 2015 內部部署部署搭配使用：

-  **CsClsRegion Cmdlet：** [CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) 、[Set-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps)、 [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps)及[Remove-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps)。
-  **CsClsSearchTerm Cmdlet：** [CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps)和[Set CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps)。
-  **CsClsSecurityGroup Cmdlet：** [CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps)、 [Set-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps)、 [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)及[Remove-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps)。

在這些 Cmdlet 中定義的設定將不會受到影響或導致任何不利的行為，但它們的設計目的是與 Microsoft Office 365 搭配使用，且不會在內部部署部署中產生預期的結果。 這不表示這些 Cmdlet 在內部部署部署中無法使用，但其使用方式是本檔中未涵蓋的更高級主題。

集中式記錄服務可以在包含單一電腦或電腦池的範圍內執行，在網站範圍（也就是已定義的網站（例如在您的部署中包含電腦和池集合的網站雷蒙德），或在全域範圍中（也就是在您部署中的所有電腦和池）。

若要使用商務用 Skype Server Management Shell 來設定集中式記錄服務範圍，您必須是 CsAdministrator 或 CsServerAdministrator 角色式存取控制（RBAC）安全性群組的成員，或是您的自訂 RBAC 角色。包含這兩個群組中的任一個。 若要傳回已指派這個 Cmdlet 的所有 RBAC 角色清單（包括您自行建立的任何自訂 RBAC 角色），請從商務用 Skype Server 管理命令介面或 Windows PowerShell 提示中執行下列命令：

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

例如：

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> 您可以在 Windows PowerShell 或 CLSController 中執行的命令列命令之間有一些基本差異。 Windows PowerShell 提供豐富的方法來設定及定義案例，並以一種有意義的方式在疑難排解案例中重複使用這些案例。 雖然 CLSController 確實提供快速且高效的方式來發出命令並取得結果，但 CLSController 的命令會受到您在命令列中提供的有限命令的限制。 與 Windows PowerShell Cmdlet 不同，CLSController 無法定義新案例、管理網站或全域階層的範圍，以及無法動態設定之有限命令集的許多其他限制。 雖然 CLSController 提供快速執行的方法，但 Windows PowerShell 提供了一種方式，可讓集中式記錄服務功能延伸到可能的 CLSController 以外。

您可以在[搜尋 CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps)（[顯示-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps)、 [Start-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps)、 [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps)、 [Sync-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps)和[Update-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps)命令）中，使用-電腦參數定義單一電腦範圍。 -電腦參數接受以逗號分隔的目的電腦完整功能變數名稱（Fqdn）清單。

> [!TIP]
> 您也可以定義池以及要執行記錄命令的逗號分隔的 [池] 清單。

[網站] 和 [全域範圍] 是在**新**的、**集合**和**移除**集中式記錄服務 Cmdlet 中定義。 下列範例示範如何設定網站和全域範圍。

> [!IMPORTANT]
> 所顯示的命令可能包含其他章節所涵蓋的參數和概念。 這個範例命令是用來示範如何使用身分**識別**參數來定義作用域，而其他參數則包括完整性並指定範圍。 如需**設定 CsClsConfiguration** Cmdlet 的詳細資料，請參閱作業檔中的[CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) 。

### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>若要取得目前的集中式記錄服務設定

1. 啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。

2. 在命令列提示處輸入下列內容：

   ```PowerShell
   Get-CsClsConfiguration
   ```

使用**新的 CsClsConfiguration**和**CsClsConfiguration** Cmdlet 來建立新的設定或更新現有的配置。當您執行**CsClsConfiguration**時，它會顯示類似下列螢幕擷取畫面的資訊，其中的部署目前具有預設的全域設定，但未定義網站配置：

![Get-CsClsConfiguration 輸出範例。](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)

### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>從電腦當地商店中取得目前的集中式記錄服務設定

1. 啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。

2. 在命令列提示處輸入下列內容：

   ```PowerShell
   Get-CsClsConfiguration -LocalStore
   ```

當您使用**CsClsConfiguration**未指定任何參數的第一個範例時，該命令會參照資料的中央管理儲存體。 如果您指定參數 LocalStore，命令會參照電腦 LocalStore，而不是中央管理儲存體。
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a>若要檢索目前定義的案例清單

1. 啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。

2. 在命令列提示處輸入下列內容：

   ```PowerShell
   Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
   ```

    例如，若要檢索在全域範圍內定義的案例：

   ```PowerShell
   Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
   ```

Cmdlet **CsClsConfiguration**會始終顯示屬於指定範圍之設定的情況。 在大多數情況下，不會顯示所有案例，而且會被截斷。 此處使用的命令會列出所有案例，以及使用哪些提供者、設定和標誌的部分資訊。
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>使用 Windows PowerShell 來更新集中式記錄服務的全域範圍

1. 啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。

2. 在命令列提示處輸入下列內容：

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   例如：

   ```PowerShell
   Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
   ```

此命令會告知部署中每個電腦和池中的 CLSAgent，將描摹檔案的滾動更新大小設定為 40 mb。 所有網站中的電腦和池都會受到命令的影響，並將其設定的追蹤記錄滾動更新值設為 40 mb。
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>使用 Windows PowerShell 來更新集中式記錄服務的網站範圍

1. 啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。

2. 在命令列提示處輸入下列內容：

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   例如：

   ```PowerShell
   Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40
   ```

> [!NOTE]
> 如範例所述，記錄檔的預設位置是%TEMP%\Tracing。 不過，因為實際 CLSAgent 正在寫入檔案並 CSLAgent [以網路服務執行]，因此% TEMP% 變數會展開為%WINDIR%\ServiceProfiles\NetworkService\AppData\Local。

此命令會告知 [網站雷蒙德] 中每個電腦和池中的 CLSAgent，將 [追蹤檔案] 上的 [翻轉] 值的大小設定為 40 mb。 在其他網站中的電腦和池不會受到命令影響，而且會繼續使用目前已設定的追蹤記錄滾動更新值（預設為 20 mb），或在記錄會話開始時使用。
### <a name="to-create-a-new-centralized-logging-service-configuration"></a>若要建立新的集中式記錄服務設定

1. 啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。

2. 在命令列提示處輸入下列內容：

   ```PowerShell
   New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
   ```

    > [!NOTE]
    > 新-CsClsConfiguration 提供大量選用設定的存取權。 如需設定選項的詳細資訊，請參閱[CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)及[瞭解集中式記錄服務設定設定](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx)。

例如，若要建立新的設定，以定義快取檔案的網路資料夾、滾動更新記錄檔的時間週期，以及記錄檔的滾動盤大小，您可以輸入：

  ```PowerShell
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

您應該仔細規劃新配置的建立，以及如何定義集中式記錄服務的新屬性。 您應該小心地進行變更，並確認您已瞭解對您能否正確記錄問題案例的影響。 您應該對設定進行變更，以增強您記錄管理的能力，讓您能夠在出現問題時進行問題的疑難排解。
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>移除現有的集中式記錄服務設定

1. 啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。

2. 在命令列提示處輸入下列內容：

   ```PowerShell
   Remove-CsClsConfiguration -Identity <scope and name>
   ```

例如，若要移除您建立的集中式記錄服務設定以增加記錄檔滾動時間，請增加滾動更新記錄檔大小，並將記錄檔案快取位置設定為網路共用，如下所示：

  ```PowerShell
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> 這是在「建立新的集中式記錄服務設定」過程中建立的新設定。

如果您選擇移除網站層級的設定，網站將會使用全域設定。
## <a name="see-also"></a>另請參閱

[設定商務用 Skype 2015 中集中式記錄服務的提供者](configure-providers.md)

[設定商務用 Skype 2015 中的集中式記錄服務的案例](configure-scenarios.md)

[商務用 Skype 2015 中的集中式記錄服務](centralized-logging-service.md)

[Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)

[CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)

[New-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csclsconfiguration?view=skype-ps)

[移除-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)

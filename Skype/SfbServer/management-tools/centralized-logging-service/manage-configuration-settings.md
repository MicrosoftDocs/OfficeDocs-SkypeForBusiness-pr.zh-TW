---
title: 在商務用 Skype Server 2015 中管理集中式記錄服務設定設定
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
description: 摘要：瞭解如何在商務用 Skype Server 2015 中針對集中式記錄服務，來取得、更新及建立設定。
ms.openlocfilehash: fb2d66e6ff72bc5fb5a4c8c987713f3ca7030ab5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098859"
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a>在商務用 Skype Server 2015 中管理集中式記錄服務設定設定

**摘要：** 瞭解如何在商務用 Skype Server 2015 中針對集中式記錄服務，取得、更新及建立設定。

集中式記錄服務是由集中式記錄服務控制器 (CLSController) 所建立及使用的設定和參數來控制及設定，將命令傳送至個別電腦的集中式記錄服務代理 (CLSAgent) 。 代理程式會處理傳送給它的命令， (並在開始命令) 使用案例的設定、提供者、追蹤持續時間及旗標開始根據所提供的設定資訊來收集追蹤記錄檔。

> [!IMPORTANT]
>  並非針對集中式記錄服務所列出的所有 Windows PowerShell Cmdlet，都適用于商務用 Skype Server 2015 內部部署。 雖然似乎可以運作，但下列 Cmdlet 並非設計為在商務用 Skype Server 2015 內部部署環境中運作：

-  **CsClsRegion Cmdlet：** [Get-CsClsRegion](/powershell/module/skype/get-csclsregion?view=skype-ps) 、[Set-CsClsRegion](/powershell/module/skype/set-csclsregion?view=skype-ps)、 [New-CsClsRegion](/powershell/module/skype/new-csclsregion?view=skype-ps)及 [Remove-CsClsRegion](/powershell/module/skype/remove-csclsregion?view=skype-ps)。
-  **CsClsSearchTerm Cmdlet：** [Get-CsClsSearchTerm](/powershell/module/skype/get-csclssearchterm?view=skype-ps) 和 [Set-CsClsSearchTerm](/powershell/module/skype/set-csclssearchterm?view=skype-ps)。
-  **CsClsSecurityGroup Cmdlet：** [Get-CsClsSecurityGroup](/powershell/module/skype/get-csclssecuritygroup?view=skype-ps)、 [Set-CsClsSecurityGroup](/powershell/module/skype/set-csclssecuritygroup?view=skype-ps)、  [New-CsClsSecurityGroup](/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)及 [Remove-CsClsSecurityGroup](/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps)。

在這些 Cmdlet 中定義的設定將不會妨礙或導致任何不良行為，但其設計目的是用於 Microsoft 365 或 Office 365，而且不會在內部部署部署中產生預期的結果。 這並不是說，在內部部署中不會使用這些 Cmdlet，但是其使用是本檔中未涵蓋的更高級主題。

集中式記錄服務可以在包含單一電腦或電腦集區的範圍中執行，也就是在網站範圍 (，也就是定義的網站（例如，包含部署) 中的電腦及集區集合），或是全域範圍 (也就是部署) 中的所有電腦及集區。

若要使用商務用 Skype Server 管理命令介面來設定集中式記錄服務範圍，您必須是 CsAdministrator 或 CsServerAdministrator 角色型存取控制 (RBAC) 安全性群組的成員，或是包含這兩個群組之任一個自訂 RBAC 角色的成員。 若要傳回所有獲指派此 Cmdlet 的 RBAC 角色清單 (包含您自行建立的自訂 RBAC 角色) ，請從商務用 Skype Server 管理命令介面或 Windows PowerShell 提示中執行下列命令：

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

例如：

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> 您可以在 Windows PowerShell 或 CLSController 中執行的命令列命令之間有基本差異。 Windows PowerShell 提供豐富的方法來設定及定義案例，並以有意義的方式針對疑難排解案例重複使用這些案例。 雖然 CLSController 提供快速且有效的方式來發出命令並取得結果，但 CLSController 的命令設定會受限於您在命令列中使用的有限命令。 與 Windows PowerShell Cmdlet 不同的是，CLSController 無法定義新案例、管理網站或全域層級的範圍，以及無法動態設定之有限命令集的其他許多限制。 雖然 CLSController 提供快速執行的方法，但 Windows PowerShell 提供一種方法來擴充集中式記錄服務功能，以超越 CLSController 的可能。

您可以在使用-computer 參數的 [Search-CsClsLogging](/powershell/module/skype/search-csclslogging?view=skype-ps)、 [Show-CsClsLogging](/powershell/module/skype/show-csclslogging?view=skype-ps)、 [Start-CsClsLogging](/powershell/module/skype/start-csclslogging?view=skype-ps)、 [Stop-CsClsLogging](/powershell/module/skype/stop-csclslogging?view=skype-ps)、 [Sync-CsClsLogging](/powershell/module/skype/sync-csclslogging?view=skype-ps) 和 [Update-CsClsLogging](/powershell/module/skype/update-csclslogging?view=skype-ps) 命令的執行期間定義單一電腦範圍。 -Computer 參數會接受以逗號分隔的完整功能變數名稱清單， (Fqdn) 目的電腦。

> [!TIP]
> 您也可以定義集區和以逗號分隔的集區清單，您想要在其上執行記錄指令。

網站和全域範圍是在 **新的**、 **集合** 及 **移除** 集中式記錄服務 Cmdlet 中定義。 下列範例會示範如何設定網站和全域範圍。

> [!IMPORTANT]
> 所顯示的命令可能包含其他章節中所涵蓋的參數和概念。 範例命令的目的是為了示範如何使用 **-Identity** 參數定義範圍，並包含其他參數的完整性，並指定範圍。 如需 **Set-CsClsConfiguration** Cmdlet 的詳細資訊，請參閱 Operations 檔中的 [Set-CsClsConfiguration](/powershell/module/skype/set-csclsconfiguration?view=skype-ps) 。

### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>若要取得目前的集中式記錄服務設定

1. 啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。

2. 在命令列提示字元處，輸入下列命令：

   ```PowerShell
   Get-CsClsConfiguration
   ```

使用 **New-CsClsConfiguration** 和 **Set-CsClsConfiguration** Cmdlet 來建立新的設定或更新現有的設定。當您執行 **Get-CsClsConfiguration** 時，它會顯示與下列螢幕擷取畫面類似的資訊，其中的部署目前具有預設全域設定，但未定義網站配置：

![Get-CsClsConfiguration 的輸出範例。](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)

### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>從電腦本地存放區中取得目前的集中式記錄服務設定

1. 啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。

2. 在命令列提示字元處，輸入下列命令：

   ```PowerShell
   Get-CsClsConfiguration -LocalStore
   ```

當您使用第一個範例，其中 **Get-CsClsConfiguration** 未指定任何參數時，此命令會參考資料的中央管理存放區。 如果您指定參數 LocalStore，此命令會參照電腦 LocalStore 而非中央管理存放區。
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a>若要取得目前定義的案例清單

1. 啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。

2. 在命令列提示字元處，輸入下列命令：

   ```PowerShell
   Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
   ```

    例如，若要檢索在全域範圍內定義的案例：

   ```PowerShell
   Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
   ```

Cmdlet **Get-CsClsConfiguration** 一定會顯示屬於特定範圍設定之部分的案例。 在大多數情況下，不會顯示所有案例，而且會被截斷。 此處所用的命令會列出使用的提供者、設定及旗標的所有案例及部分資訊。
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>使用 Windows PowerShell 更新集中式記錄服務的全域範圍

1. 啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。

2. 在命令列提示字元處，輸入下列命令：

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   例如：

   ```PowerShell
   Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
   ```

命令會告訴部署中每台電腦及集區上的 CLSAgent，將追蹤檔案的變換值大小設定為 40 mb。 所有網站中的電腦與集區都會受到命令的影響，並會將其設定的追蹤記錄檔翻轉值設定為 40 mb。
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>使用 Windows PowerShell 更新集中式記錄服務的網站範圍

1. 啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。

2. 在命令列提示字元處，輸入下列命令：

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   例如：

   ```PowerShell
   Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40
   ```

> [!NOTE]
> 如範例中所述，記錄檔的預設位置是%TEMP%\Tracing。 不過，由於實際 CLSAgent 是寫入檔案，而 CSLAgent 以網路服務方式執行，所以%TEMP% 變數會擴充為%WINDIR%\ServiceProfiles\NetworkService\AppData\Local。

命令會告訴 site Redmond 中每一部電腦及集區上的 CLSAgent，將追蹤檔案的變換值大小設定為 40 mb。 其他網站中的電腦及集區不會受到命令的影響，而且會繼續使用目前設定的追蹤記錄檔滾動更新值，此值是由預設 (20 mb) 或開始記錄會話期間所定義。
### <a name="to-create-a-new-centralized-logging-service-configuration"></a>若要建立新的集中式記錄服務設定

1. 啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。

2. 在命令列提示字元處，輸入下列命令：

   ```PowerShell
   New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
   ```

    > [!NOTE]
    > New-CsClsConfiguration 提供大量選用設定設定的存取權。 如需設定選項的詳細資訊，請參閱 [Get-CsClsConfiguration](/powershell/module/skype/get-csclsconfiguration?view=skype-ps) 和 [瞭解集中式記錄服務設定設定](/previous-versions/office/lync-server-2013/lync-server-2013-understanding-centralized-logging-service-configuration-settings)。

例如，若要建立新的設定以定義快取檔案的網路資料夾、滾動表檔的記錄檔和翻轉大小的時間週期，您可以輸入：

  ```PowerShell
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

您應該仔細規劃新設定的建立，以及如何定義集中式記錄服務的新屬性。 您應謹慎進行變更，並確定您瞭解能夠正確記錄問題案例的影響。 您應該對設定進行變更，以增強您記錄管理大小的能力，以及可在發生問題時進行問題解決的翻轉期間。
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>移除現有的集中式記錄服務設定

1. 啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。

2. 在命令列提示字元處，輸入下列命令：

   ```PowerShell
   Remove-CsClsConfiguration -Identity <scope and name>
   ```

例如，若要移除您已建立的集中式記錄服務設定，以增加記錄檔翻轉時間、增加翻轉記錄檔大小，並將記錄檔快取位置設為網路共用，如下所示：

  ```PowerShell
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> 這是在「建立新的集中式記錄服務設定」過程中建立的新設定。

如果您選擇移除網站層級設定，則網站會使用通用設定。
## <a name="see-also"></a>另請參閱

[在商務用 Skype Server 2015 中設定集中式記錄服務的提供者](configure-providers.md)

[在商務用 Skype Server 2015 中設定集中式記錄服務的案例](configure-scenarios.md)

[商務用 Skype 2015 中的集中式記錄服務](centralized-logging-service.md)

[Set-CsClsConfiguration](/powershell/module/skype/set-csclsconfiguration?view=skype-ps)

[Get-CsClsConfiguration](/powershell/module/skype/get-csclsconfiguration?view=skype-ps)

[New-CsClsConfiguration](/powershell/module/skype/new-csclsconfiguration?view=skype-ps)

[Remove-CsClsConfiguration](/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)
---
title: 設定 2015 年 商務用 Skype Server集中式記錄服務的案例
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
description: 摘要：瞭解如何在 2015 年 商務用 Skype Server 建立、修改和移除集中式記錄服務的案例。
ms.openlocfilehash: ecd96dc849030cb035f965c8cb52eb7607bd9667
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676355"
---
# <a name="configure-scenarios-for-the-centralized-logging-service-in-skype-for-business-server-2015"></a>設定 2015 年 商務用 Skype Server集中式記錄服務的案例

**總結：** 瞭解如何在 2015 商務用 Skype Server中建立、修改和移除集中式記錄服務的案例。

案例會定義範圍 (，也就是全域、網站、集區或電腦) ，以及要在集中式記錄服務中使用的提供者。 藉由使用案例，您可以在提供者 (上啟用或停用追蹤，例如 S4、SIPStack、IM 和 Presence) 。 藉由設定案例，您可以將特定邏輯集合的所有提供者分組，以解決特定問題條件。 如果您發現需要修改案例以符合您的疑難排解和記錄需求，商務用 Skype Server 2015 偵錯工具會提供名為 ClsScenarioEdit.psm1 的Windows PowerShell模組，其中包含名為Edit-CsClsScenario 的函式。 模組的目的是要編輯具名案例的屬性。 本主題提供此課程模組運作方式的範例。 請先下載 商務用 Skype Server 2015[偵錯工具](https://go.microsoft.com/fwlink/p/?LinkId=285257)，再繼續進行。

> [!IMPORTANT]
> 針對任何指定的範圍—月臺、全域、集區或電腦—您可以在任何指定時間執行最多兩個案例。 若要判斷目前正在執行的案例，請使用 Windows PowerShell 和[Get-CsClsScenario](/powershell/module/skype/get-csclsscenario)。 藉由使用 Windows PowerShell 和[Set-CsClsScenario](/powershell/module/skype/set-csclsscenario)，您可以動態變更正在執行的案例。 您可以修改在記錄會話期間執行的案例，以調整或精簡您要收集的資料，以及從哪些提供者進行調整。

若要使用 商務用 Skype Server 管理命令介面來執行集中式記錄服務函式，您必須是 CsAdministrator 或 CsServerAdministrator 角色型存取控制 (RBAC) 安全性群組的成員，或包含這兩個群組之一的自訂 RBAC 角色。 若要傳回已指派此 Cmdlet 的所有 RBAC 角色清單，包括您自己建立的任何自訂 RBAC 角色，請從 商務用 Skype Server 管理命令介面或Windows PowerShell提示字元執行下列命令：

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

例如：

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

本主題的其餘部分著重于如何定義案例、修改案例、擷取執行中的案例、移除案例，以及指定案例包含的內容，以優化您的疑難排解。 您可以使用 商務用 Skype Server 管理命令介面來發出Windows PowerShell命令。 當您使用Windows PowerShell時，您可以定義要在記錄會話中使用的新案例。

如[2015 年 商務用 Skype 集中式記錄服務中](centralized-logging-service.md)所介紹，案例的元素如下：

- **供應商** 如果您熟悉 OCSLogger，提供者是您選擇告訴 OCSLogger 追蹤引擎應該從中收集記錄的元件。 提供者是相同的元件，而且在許多情況下，其名稱與 OCSLogger 中的元件相同。 如果您不熟悉 OCSLogger，則提供者是集中式記錄服務可以從中收集記錄的伺服器角色特定元件。 如需提供者設定的詳細資訊，[請參閱在 2015 商務用 Skype Server中設定集中式記錄服務的提供者](configure-providers.md)。

- **身份** 參數 -Identity 會設定案例的範圍和名稱。 例如，您可以設定「全域」的範圍，並使用 「LyssServiceScenario」 來識別案例。 當您結合兩者時，您會定義 Identity (例如「global/LyssServiceScenario」) 。

    您可以選擇性地使用 -Name 和 -Parent 參數。 您可以定義 Name 參數來唯一識別案例。 如果您使用 Name，則也必須使用 Parent 將案例新增至全域或網站。

    > [!IMPORTANT]
    > 如果您使用 Name 和 Parent 參數，就無法使用 **-Identity** 參數。

## <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a>使用 New-CsClsScenario Cmdlet 建立新案例

1. 啟動商務用 Skype Server管理命令介面：依序按一下 [**開始**]、[**所有程式]** 和 **[商務用 Skype 2015**]，然後按一下 **[商務用 Skype Server 管理命令介面]**。

2. 若要建立記錄會話的新案例，請使用 [New-CsClsProvider](/powershell/module/skype/new-csclsprovider) 並定義案例的名稱 (也就是如何唯一識別) 。 從 WPP (中選擇記錄格式類型，也就是Windows軟體追蹤預處理器，並且是預設) 、EventLog (，也就是Windows事件記錄檔格式) 或 IISLog (，也就是根據 IIS 記錄檔格式) 的 ASCII 格式檔案。 接下來，將層級 (定義為本主題) 中記錄層級底下的定義，以及) 本主題的 Flags 下定義的 Flags (。

    在此範例案例中，我們使用 LyssProvider 作為範例提供者變數。

    若要使用定義的選項建立案例，請輸入：

   ```PowerShell
   New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
   ```

    例如：

   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
   ```

    使用 -Name 和 -Parent 的替代格式：

   ```PowerShell
   New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider
   ```

## <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a>使用 New-CsClsScenario Cmdlet 建立具有多個提供者的新案例

1. 啟動商務用 Skype Server管理命令介面：依序按一下 [**開始**]、[**所有程式]** 和 **[商務用 Skype 2015**]，然後按一下 **[商務用 Skype Server 管理命令介面]**。

2. 每個範圍只能有兩個案例。 不過，您不限於一定數目的提供者。 在此範例中，假設我們已建立三個提供者，而您想要將這三個全部指派給您要定義的案例。 提供者變數名稱為 LyssProvider、ABServerProvider 和 SIPStackProvider。 若要定義多個提供者並指派給案例，請在商務用 Skype Server管理命令介面或Windows PowerShell命令提示字元輸入下列命令：

   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
   ```

    > [!NOTE]
    > 如Windows PowerShell中所述，使用 `@{<variable>=<value1>, <value2>, <value>...}` 建立值雜湊表的慣例稱為「展開」。 如需在 Windows PowerShell 中展開的詳細資訊，請參閱 [https://go.microsoft.com/fwlink/p/?LinkId=267760](/previous-versions/technet-magazine/gg675931(v=msdn.10)) 。

## <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a>使用 Set-CsClsScenario Cmdlet 修改現有的案例

1. 啟動商務用 Skype Server管理命令介面：依序按一下 [**開始**]、[**所有程式]** 和 **[商務用 Skype 2015**]，然後按一下 **[商務用 Skype Server 管理命令介面]**。

2. 每個範圍只能有兩個案例。 您可以隨時變更正在執行的案例，即使記錄擷取會話正在進行。 如果您重新定義執行中的案例，目前的記錄會話將會停止使用已移除的案例，然後開始使用新的案例。 不過，已移除案例所擷取的記錄資訊會保留在擷取的記錄檔中。 若要定義新案例，請執行下列 (，也就是假設新增名為 「S4Provider」 的已定義提供者) ：

   ```PowerShell
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
   ```

    例如：

   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
   ```

    如果您想要取代提供者，請定義單一提供者或以逗號分隔的提供者清單，以取代目前的集合。 如果您只想要取代許多提供者的其中一個，請將目前的提供者新增至新的提供者，以建立一組包含新提供者和現有提供者的新提供者。 若要以新集合取代所有提供者，請輸入下列內容：

   ```PowerShell
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
   ```

    例如，若要將目前的$LyssProvider、$ABServerProvider和$SIPStackProvider集取代為 $LyssServiceProvider：

   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
   ```

    若只要將目前$LyssProvider集、$ABServerProvider和$SIPStackProvider中的$LyssProvider提供者取代為 $LyssServiceProvider，請輸入下列內容：

   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}
   ```

## <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a>使用 Remove-CsClsScenario Cmdlet 移除現有的案例

1. 啟動商務用 Skype Server管理命令介面：依序按一下 [**開始**]、[**所有程式]** 和 **[商務用 Skype 2015**]，然後按一下 **[商務用 Skype Server 管理命令介面]**。

2. 如果您想要移除先前定義的案例，請輸入下列內容：

   ```PowerShell
   Remove-CsClsScenario -Identity <name of scope and scenario>
   ```

    例如，若要移除定義的案例網站：Redmond/LyssServiceScenario：

   ```PowerShell
   Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"
   ```

**Remove-CsClsScenario** Cmdlet 會移除指定的案例，但已擷取的追蹤仍可在記錄中供您搜尋。

## <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clsscenarioeditpsm1-module"></a>使用 ClsScenarioEdit.psm1 模組載入和卸載 Edit-CsClsScenario Cmdlet

1. 啟動商務用 Skype Server管理命令介面：依序按一下 [**開始**]、[**所有程式]** 和 **[商務用 Skype 2015**]，然後按一下 **[商務用 Skype Server 管理命令介面]**。

    > [!IMPORTANT]
    > ClsScenarioEdit.psm1 模組會以個別的 Web 下載方式提供。 模組是 商務用 Skype Server 2015 偵錯工具的一部分。 根據預設，偵錯工具會安裝在 C：\Program Files\商務用 Skype Server 2015\Debugging Tools 目錄中。

2. 從Windows PowerShell中，輸入：

   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > 成功載入模組會將您傳回Windows PowerShell命令提示字元。 若要確認已載入模組，且Edit-CsClsScenario可用，請輸入  `Get-Help Edit-CsClsScenario` 。 您應該會看到 EditCsClsScenario 語法的基本語法。

3. 若要卸載模組，請輸入：

   ```PowerShell
   Remove-Module ClsController
   ```

    > [!TIP]
    > 成功卸載模組會將您傳回Windows PowerShell命令提示字元。 若要確認模組已卸載，請輸入  `Get-Help Edit-CsClsScenario` 。 Windows PowerShell會嘗試尋找 Cmdlet 的說明並失敗。

## <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a>使用 Edit-ClsController 模組從案例中移除現有的提供者

1. 啟動商務用 Skype Server管理命令介面：依序按一下 [**開始**]、[**所有程式]** 和 **[商務用 Skype 2015**]，然後按一下 **[商務用 Skype Server 管理命令介面]**。

2. 從Windows PowerShell中，輸入：

   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > 成功載入模組會將您傳回Windows PowerShell命令提示字元。 若要確認已載入模組，且Edit-CsClsScenario可用，請輸入  `Get-Help Edit-CsClsScenario` 。 您應該會看到 EditCsClsScenario 語法的基本語法。

3. 若要從 AlwaysOn 案例中移除提供者，請輸入：

   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
   ```

   例如：

   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
   ```

   ScenarioName 和 ProviderName 參數是位置 (也就是說，它們必須在命令列中的預期位置中定義) 參數。 如果案例名稱位於第二個位置，且提供者位於位置 3，相對於 Cmdlet 的名稱做為位置 1，則不需要明確定義參數名稱。 使用這項資訊，先前的命令會輸入為：

   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Remove
   ```

   參數值的位置放置僅適用于 -Scenario 和 -Provider。 所有其他參數都必須明確定義。

## <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a>使用 Edit-ClsController 模組將提供者新增至案例

1. 啟動商務用 Skype Server管理命令介面：依序按一下 [**開始**]、[**所有程式]** 和 **[商務用 Skype 2015**]，然後按一下 **[商務用 Skype Server 管理命令介面]**。

2. 若要將提供者新增至 AlwaysOn 案例，請輸入：

   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
   ```

    例如：

   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
   ```

    -Loglevel 的類型可以是 Fatal、Error、Warning、Info、Verbose、Debug 或 All。 -Flags 可以是提供者支援的任何旗標，例如TF_COMPONENT、TF_DIAG。 -Flags 也可以是值 ALL

   先前的範例也可以使用 Cmdlet 的位置功能來輸入。 例如，若要將提供者 ChatServer 新增至 AlwaysOn 案例，請輸入：

   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL
   ```

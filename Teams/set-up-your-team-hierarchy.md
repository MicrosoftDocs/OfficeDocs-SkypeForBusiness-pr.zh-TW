---
title: 設定您的團隊目標階層
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: andfried, acolonna
search.appverid: MET150
description: 瞭解如何在組織中設定小組階層，將內容發佈至一組大型團隊。
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a801ae905ac7c384399aea5ccdf3bcf6f4e4200f
ms.sourcegitcommit: 4d2e1328dee2b6c60ba0022976da8dfe5efba2ef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2021
ms.locfileid: "53203612"
---
# <a name="set-up-your-team-targeting-hierarchy"></a>設定您的團隊目標階層

設定團隊目標階層會允許貴組織將內容發佈至一組大型團隊。 團隊目標階層會定義階層中所有團隊彼此關聯、哪些使用者可以發佈工作，以及哪些團隊使用者有權發佈工作。 除非為貴組織設定小組目標階層，否則所有使用者的發佈功能都停用。 若要設定團隊目標階層，您必須建立定義階層的檔案，然後將它上傳到 Teams以將其套用至您的組織。 架構上傳之後，Teams內的應用程式就可以使用它。

> [!IMPORTANT]
> 在初次發行中，只有工作應用程式支援階層式團隊。  將小組目標階層適用于貴組織後 [，就會在](https://support.microsoft.com/office/publish-task-lists-to-create-and-track-work-in-your-organization-095409b3-f5af-40aa-9f9e-339b54e705df) 工作應用程式中啟用任務發佈。 您不會在團隊的Microsoft Teams。

以下範例說明階層在 Teams 中如何Teams。 建立工作清單之後，發佈小組成員就可以選取要傳送的收件者團隊 (發佈) 清單。 選取團隊時，發佈小組可以按照階層、屬性或兩者的組合來篩選。<br>

![ [工作發佈] 的螢幕擷取畫面](media/manage-tasks-app-publish.png)

## <a name="terminology"></a>術語

當您流覽階層時，下列字詞非常重要。 Teams會 **稱為節點。**

* **根節點** 是階層中最上方的節點。 在範例中，Retail Communications 是根節點。
* **父節點****和子節點** 是代表兩個連接節點之間關聯性的條款。 在範例中，地區 01 是區域 1 的子節點。
* 多個層級的子代稱為 **子代**。 區 01、市/市 01、市/市 03、市/市 07、區 02 和區 03 都是區域 1 的後代。
* 沒有子節點的節點稱為葉 **節點**。 它們位於階層的底部。
* **收件** 者團隊是已選取以接收要發佈之特定內容集的團隊。 它們必須是葉節點。

## <a name="plan-your-hierarchy"></a>規劃階層

在建立定義階層的架構之前，您需要進行一些規劃，並決定要如何塑造您的組織。  第一個優先順序是決定哪些組織群組需要將工作發佈至其他群組。 階層中的每個節點代表工作組或群組。

### <a name="permissions-to-publish"></a>發佈許可權

發佈許可權取決於使用者是階層中任何團隊的成員，以及該團隊或一組團隊與階層中其他團隊的關係。

> [!NOTE]
> 團隊的擁有者也會獲得發佈許可權。

* 如果使用者是至少一個團隊的成員，且該團隊的階層中至少有一個子代，該使用者可以發佈至這些子代，而不必成為所有想要發佈之團隊的成員。
* 如果使用者是階層中至少一個團隊的成員，但並非階層中具有子代的任何團隊的成員，該使用者就可以查看並接收其組織發佈的內容。
* 如果使用者不是階層中任何團隊的成員，該使用者將不會看到任何發佈相關功能。

### <a name="guidelines"></a>指引

* 每個組織只能有一個階層檔案。 不過，您可以在一個 CSV 檔案中，將貴組織的不同部分組成不同的節點階層。 例如，Contoso Pharmaceuticals 有一個 Pharmaceuticaly 根節點和零售根節點。 這兩個根節點有多個子代列，而且兩者之間沒有重迭。
* 只有葉節點可以是出版物的收件者。 階層中的其他節點有助於選取出版物的收件者。
* 團隊只能在階層中顯示一次。
* 階層可以包含最多 15，000 個節點。 我們計畫與客戶合作，提高大型組織的此限制。

### <a name="example-hierarchy"></a>範例階層

例如，在下列階層中，回收、通訊和人力資源可以將工作發佈至階層中的每個下層節點 (小組) ，但西北區只能將工作發佈至紐約市和波士頓市管理區團隊。 範例階層可讓回收、通訊和人力資源群組發佈適用于整個公司的工作，例如福利資訊或來自 CEO 的郵件。 僅將人員排程、天氣資訊等工作發佈給紐約市和波士頓市管理區團隊。

![團隊階層式範例](media/team-targeting-schema-example-new.png)

## <a name="create-your-hierarchy"></a>建立階層

> [!NOTE]
> 本文的其餘部分會討論在將工作發佈給收件者團隊時設定團隊階層。 請參閱在 Teams 中管理貴組織的工作應用程式，[以概](./manage-tasks-app.md)觀瞭解工作應用程式，其中任務發佈在啟用時會出現。

定義階層的架構是以 CSV 檔案中的逗號分隔值 () 為基礎。 CSV 檔案中的每個列對應至團隊階層中的一個節點。 每一列都包含為階層內節點命名的資訊，選擇性地將節點連結至團隊，以及可用於篩選支援該節點之應用程式中團隊的屬性。

您也可以定義資料桶 **，這是** 發佈小組可用於組織送出給收件者團隊的內容的類別，讓他們更容易查看、排序及專注于相關內容。

### <a name="add-required-columns"></a>新增必要的欄

CSV 檔案必須包含下列三欄，從第一欄開始的順序如下。 節點必須連結至小組，它若要接收工作。

| 欄名稱   | 必要 | 說明   |
----------------|----------|---------------|
| DisplayName    | 是      | 此欄位是節點的名稱。 名稱最多隻能有 100 個字元，而且只包含 A-Z、a-z 和 0-9 的字元。 節點名稱必須是唯一的。 |
| ParentName    | 是       | 這是父節點的名稱。 您在這裡指定的值必須與父節點 **的 DisplayName** 欄位中的值完全相符。 如果您想要新增多個父節點，請以分號分隔每個父節點名稱， () 。 您最多可以新增 25 個父節點，且每個父節點名稱最多 2500 個字元。 只有在父節點是根節點時，節點才能有多個父節點。   <br><br>**重要** 請小心不要建立一個迴圈，讓階層中較高階層的父節點參照階層中的下層子節點。 不支援這項功能。 |
| TeamId        | 是，如果小組發佈工作或接收來自父節點的工作       | 這包含要連結節點的團隊識別碼。 每個節點都必須參照唯一的團隊，因此每個 TeamId 值可能只會出現在階層檔案中一次。 若要取得要連結節點的團隊識別碼，請執行下列 PowerShell 命令 `Get-Team | Export-Csv TeamList.csv` ：。 此命令會列出貴組織中團隊，並包含每個團隊的名稱和識別碼。 尋找您想要連結的團隊名稱，然後將識別碼複製到此欄位。|

> [!NOTE]
> 如果節點不是根節點或葉節點，而且您不需要團隊成員資格來授予發佈和報表的對應許可權，您可以將 TeamId 保留空白。 這個方法可用來在選擇收件者團隊時增加更精細的細度，或在沒有對應小組的情況下檢視完成報告。

### <a name="add-attribute-columns"></a>新增屬性欄

新增三個必填欄之後，您可以新增選擇性屬性欄。 這些屬性可用來篩選節點，以便更輕鬆地選取要發佈工作的屬性。 根據該屬性的值是否互斥，定義屬性的方法有兩種。

|新增屬性的方法|說明 |範例  |
|---|---------|---------|
|如果屬性的值是互斥的，您指定的欄名稱會變成屬性的名稱。|每一列可以包含一個屬性值，而每個屬性欄最多可以有 50 個唯一值。 每個值最多隻能有 100 個字元。 當您使用團隊目標階層選取收件者團隊時，在屬性欄中指定的一組屬性值會顯示為該屬性的篩選值。|您希望使用者能夠根據版面配置篩選儲存空間。 這個屬性的值是互斥的，因為商店只能有一個版面配置。 <br><br>若要新增屬性以根據版面配置篩選商店，請新增名為 Store 版面配置的資料行。 在此範例中，Store 版面配置屬性的值為壓縮、標準及大型。
|如果您需要為屬性指定多個值，而且這些值並非互斥，請使用 **屬性名稱：UniqueValue** 格式作為欄名。 <br><br>**重要** 請確定使用僅英文冒號 (：) unicode 不支援做為屬性欄分隔符號。 |冒號前的文字字串 (：) 成為屬性的名稱。 在冒號 (：) 前包含相同文字字串的所有欄，會分組到篩選功能表中的節。 冒號後的每個字串都會變成該節的值。<br><br>每一列的值為 0 (0 或 1) 屬性為 1。 值為 0 表示屬性不適用於節點，而值為 1 表示屬性會適用于該節點。|您希望使用者能夠根據部門篩選儲存區。 商店可以有多個部門，因此此屬性的值並非互斥。<br><br>在此範例中，我們新增部門：服裝、部門：電子、部門：食物、部門：住家和園藝、部門：運動用品做為屬性欄。 部門會變成屬性名稱，使用者可以根據服裝、電子、食物、住家園藝和運動用品部門進行篩選。|

當您新增屬性欄時，請記住下列事項：

* 您指定的欄名稱或在冒號 (：) 之前指定的欄名稱，會成為屬性的名稱。 此值會顯示在使用該階層Teams應用程式。
* 您階層中最多可以有 50 個屬性欄。
* 欄名稱最多隻能有 100 個字元，而且只包含 A-Z、a-z 和 0-9 的字元，以及空格。 欄名稱必須是唯一的。

### <a name="add-bucket-columns"></a>新增資料桶欄

您可以新增資料桶欄以建立可以組織工作之群組的容器。 每個容器在 CSV 檔案中都有自己的欄。 您建立的水桶可供發佈小組使用。 發佈小組就可以使用這些資料桶來分類收件者團隊的工作。 如果團隊中還沒有一個資料桶，當發佈任務時，即會根據需求建立資料桶。

發佈小組可以集中將工作專案分類一次，為收到工作清單的所有數十個、數百個或數千個收件者小組預先組織工作清單。 然後，收件者小組可以排序及篩選工作，以專注于與工作最相關的區域。

當您新增資料桶欄時，請注意下列事項：

* 欄名稱會變成資料桶的名稱。 您指定的每個資料桶都會出現在使用階層的 Teams中。
* 建議您不要在容器名稱中納入敏感性資訊。 目前，發佈小組無法透過建立後發佈來移除資料桶。
* 欄名稱前面必須有一個雜湊標記 (#) 。 它最多隻能有 100 個字元，而且只包含 A-Z、a-z 和 0-9 的字元。 例如，#Operations和#Frozen貨物。
* 階層可以包含最多 25 個數據桶欄。 我們計畫與客戶合作，為較大的組織提高此限制。

### <a name="example"></a>範例

以下是架構 CSV 檔案的範例，該檔案會建立以支援上一個影像中顯示的階層。 此架構包含下列專案：

* 三個名為 `TargetName` 、 `ParentName` 和 的必填欄 `TeamId`
* 三個名為 `Store layout` 、 `Departments:Clothing` 和 的屬性欄 `Departments:Foods`
* 名稱為 、和 的三個數據桶 `Fresh Foods` `Frozen Foods` 欄 `Women's Wear`

屬性 `Store layout` 具有包含 、和 `Compact` `Standard` 的值 `Large` 。 屬性 `Departments` 欄可設定為零或 (`0`) 的值 `1` 。 上述 `Store` 影像不會顯示版面配置 `Departments` 和屬性。 它們新增在這裡，可協助顯示如何將屬性新加到節點專案。 這三個數據桶欄也是如此。

```CSV
TargetName,ParentName,TeamId,Store layout,Departments:Clothing,Departments:Foods,#Fresh Foods,#Frozen Foods,#Women's Wear
Recall,,db23e6ba-04a6-412a-95e8-49e5b01943ba,,,,,,
Communications,,145399ce-a761-4843-a110-3077249037fc,,,,,,
HR,,125399ce-a761-4983-a125-3abc249037fc,,,,,,
East Regional Office,HR;Communications;Recall,,,,,,,
West Regional Office,HR;Communications;Recall,,,,,,,
Northeast Zone,East Regional Office,,,,,,,
Southeast Zone,East Regional Office,,,,,,,
New York Store,Northeast Zone,e2ba65f6-25e7-488b-b8f0-b8562d5de60a,Large,1,1,,,
Boston Store,Northeast Zone,0454f08a-0507-437c-969a-682eb2fae7fc,Standard,1,1,,,
Miami Store,Southeast Zone,619d6e4e-5f68-4b36-8e1f-16c98d7396c1,Compact,0,1,,,
New Orleans Store,Southeast Zone,6be960b8-72af-4561-a343-9ac4711874eb,Compact,0,1,,,
Seattle Store,West Regional Zone,487c0d20-4e55-4dc2-8187-a24c826e0fee,Standard,1,1,,,
Los Angeles Store,West Regional Zone,204a1287-2efb-4a8a-88e0-56fbaf5a2389,Large,1,1,,,
```

## <a name="apply-your-hierarchy"></a>使用階層

> [!NOTE] 
> 若要執行此步驟，您必須從 PowerShell 圖庫Teams PowerShell 公用預覽模組。 有關如何安裝模組的步驟，請參閱在 PowerShell Teams安裝。

> [!NOTE]
> 政府社群雲端 (GCC) 必須使用 Cmdlet 預覽版本[2.4.0-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.4.0-preview)或更新版本，以確保資料會路由至 GCC 環境，而非公用雲端環境。

在架構 CSV 檔案中定義階層之後，就可以將階層上傳到Teams。 若要這麼做，請執行下列命令。 您必須是全域系統管理員或Teams系統管理員才能執行此步驟。

```powershell
Set-TeamTargetingHierarchy -FilePath "C:\ContosoTeamSchema.csv"
```

### <a name="update-your-hierarchy"></a>更新階層

您可以使用與上述相同的 PowerShell 命令上傳新階層以取代舊階層。 每當您上傳新階層時，它會取代先前的階層。

### <a name="check-the-status-of-your-hierarchy"></a>檢查階層狀態

您可以執行下列命令來檢查階層上傳的狀態。

```powershell
Get-TeamTargetingHierarchyStatus
```

該命令會返回下欄欄位：

領域|說明
-----|------------
Id | 上傳的唯一識別碼。
地位 | Upload狀態。 值包括 **開始**、**驗證****、成功** 和 **失敗**
ErrorDetails | 如果上傳錯誤，詳細資料。 有關錯誤詳細資料的詳細資訊，請參閱疑難排解一節。 如果沒有錯誤，此欄位為空白。
LastUpdatedAt | 檔案上次更新的時間戳記和日期。
LastModifiedBy | 上次修改檔案的使用者識別碼。
檔案名 | CSV 的檔案名。

## <a name="remove-your-hierarchy"></a>移除階層

如果您想要立即停用貴組織中所有使用者的已發佈清單選項卡，您可以移除您的階層。 使用者無法存取的已發佈清單選項卡或該選項卡上的任何功能。 這包括建立要發佈的新工作清單、存取草稿清單、發佈、取消發佈和重複清單，以及查看報告。 移除階層不會取消發佈先前發佈的工作。 這些工作仍然可供收件者小組完成。

若要移除階層，請執行下列命令。 您必須是系統管理員才能執行此步驟。

```powershell
Remove-TeamTargetingHierarchy
```

確認刪除時，狀態訊息仍然會顯示先前的架構存在，但嘗試再次刪除時，會返回物件為 Null 的錯誤。

## <a name="create-a-sample-hierarchy"></a>建立範例階層

### <a name="install-the-teams-powershell-module"></a>安裝 powerShell Teams模組

> [!IMPORTANT]
> 若要執行此步驟，您必須從 PowerShell 圖庫安裝Teams PowerShell 公用預覽[模組](https://www.powershellgallery.com/packages/MicrosoftTeams/)。 若要瞭解如何安裝模組的步驟，請參閱在[PowerShell Teams安裝](teams-powershell-install.md)。

### <a name="sample-script"></a>範例腳本

下列腳本可用來建立團隊，並上傳.csv檔案Microsoft Teams租使用者。 如果您有現有的階層，此腳本會取代它。

#### <a name="create-teams-for-a-simple-hierarchy"></a>建立簡單階層的團隊

```powershell
$tm1 = New-Team -DisplayName "HQ"
$tm2 = New-Team -DisplayName "North"
$tm3 = New-Team -DisplayName "Store 1"
$tm4 = New-Team -DisplayName "Store 2"
$tm5 = New-Team -DisplayName "South"
$tm6 = New-Team -DisplayName "Store 3"
$tm7 = New-Team -DisplayName "Store 4"
```

#### <a name="use-team-data-to-create-comma-separated-output-displayname-parentname-teamid"></a>使用小組資料建立以逗號分隔的輸出 (DisplayName、ParentName、TeamId) 

```powershell
$csvOutput = "DisplayName" + "," + "ParentName" + "," + "TeamId" + "`n"
$csvOutput = $csvOutput + $tm1.DisplayName + "," + "," + $tm1.GroupID + "`n"
$csvOutput = $csvOutput + $tm2.DisplayName + "," + $tm1.DisplayName + "," + $tm2.GroupID + "`n"
$csvOutput = $csvOutput + $tm3.DisplayName + "," + $tm2.DisplayName + "," + $tm3.GroupID + "`n"
$csvOutput = $csvOutput + $tm4.DisplayName + "," + $tm2.DisplayName + "," + $tm4.GroupID + "`n"
$csvOutput = $csvOutput + $tm5.DisplayName + "," + $tm1.DisplayName + "," + $tm5.GroupID + "`n"
$csvOutput = $csvOutput + $tm6.DisplayName + "," + $tm5.DisplayName + "," + $tm6.GroupID + "`n"
$csvOutput = $csvOutput + $tm7.DisplayName + "," + $tm5.DisplayName + "," + $tm7.GroupID 
```

#### <a name="save-output-to-a-csv-file-in-the-downloads-folder"></a>將輸出儲存到 .csv 資料夾中 **的檔案**

```powershell
$csvOutputPath = $env:USERPROFILE + "\downloads\testhierarchy-" + (Get-Date -Format "yyyy-MM-dd-hhmmss") + ".csv" 
$csvOutput | Out-File $csvOutputPath
```

#### <a name="upload-the-hierarchy"></a>Upload階層

```powershell
Set-TeamTargetingHierarchy -FilePath $csvOutputPath
Get-TeamTargetingHierarchyStatus
```

## <a name="troubleshooting"></a>疑難排解

### <a name="how-to-view-error-details"></a>如何查看錯誤詳細資料

您可以執行下列命令以瞭解導致錯誤的原因，並返回錯誤詳細資料。

```powershell
(Get-TeamTargetingHierarchyStatus).ErrorDetails.ErrorMessage
```

### <a name="you-receive-an-error-message-when-you-upload-your-schema-csv-file"></a>上傳架構 CSV 檔案時，您會收到錯誤訊息

請注意錯誤訊息，因為錯誤訊息應包含疑難排解資訊，指出無法上傳架構的原因。 根據錯誤訊息中的資訊來檢查和編輯架構 CSV 檔案，然後再試一次。

### <a name="you-receive-an-error-invalidteamid-error-message-when-you-upload-your-schema-csv-file"></a>上傳架構 CSV 檔案時，您會收到「錯誤：無效TeamId」錯誤訊息

當您嘗試上傳架構 CSV 檔案時，您收到下列錯誤訊息：

```console
Error: InvalidTeamId
Description: TeamID in row # doesn't match a valid Group ID. Please view our documentation to learn how to get the proper GroupID for each team.
```

檢查以確保您為架構 CSV 檔案中的小組使用正確的 TeamId。 TeamId 應該與支援小組之Microsoft 365群組的組識別碼相同。 您可以在系統管理中心中Microsoft Teams群組識別碼。

1. 在系統管理中心的左側導 [Microsoft Teams，請](https://admin.teams.microsoft.com/)**前往** Teams  >  **Teams**。
2. 如果 **表格中未** 顯示群組識別碼欄，請選取表格右上角的編輯欄，然後開啟 **群組識別碼**。
3. 在清單中尋找團隊，然後找出組識別碼。

請確定架構 CSV 檔案中的 TeamId 符合系統管理中心中顯示的組Microsoft Teams識別碼。

## <a name="related-topics"></a>相關主題

* [在 Teams](manage-tasks-app.md)
* [Teams PowerShell 概觀](teams-powershell-overview.md)

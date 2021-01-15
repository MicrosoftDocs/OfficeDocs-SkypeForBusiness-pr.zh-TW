---
title: 設定您的團隊目標階層
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: andfried, acolonna
search.appverid: MET150
description: 瞭解如何在組織中設定小組階層，以將內容發佈至大型小組。
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0c5a0fcdce1218bc32eac8b28e7a8c1f41e87cb0
ms.sourcegitcommit: 9787b84ab15ee2e14890151e966c81b4a4d43e62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/14/2021
ms.locfileid: "49868338"
---
# <a name="set-up-your-team-targeting-hierarchy"></a>設定您的團隊目標階層

設定團隊目標階層可讓您的組織將內容發佈至大型小組。 團隊目標階層定義層次結構中的所有團隊如何彼此關聯，哪些使用者可以發佈工作，以及使用者有權發佈至哪些團隊。 除非針對您的組織設定團隊目標階層，否則所有使用者都停用發佈功能。 若要設定團隊目標階層，您需要建立一個定義階層的檔案，然後將其上傳至團隊，將其套用到您的組織。 上傳架構之後，小組中的 app 就可以使用它。

> [!IMPORTANT]
> 初次發行時，只有 [任務] app 支援階層式團隊。  將團隊目標階層套用至您的組織將會在 [工作] app 中啟用 [任務發佈](https://support.microsoft.com/office/publish-task-lists-to-create-and-track-work-in-your-organization-095409b3-f5af-40aa-9f9e-339b54e705df) 。 在 Microsoft 團隊的其他區域中，您不會看到小組的階層。

以下是在 [團隊] 中的 [工作] 應用程式中代表階層的範例。 在工作清單建立之後，發佈小組的成員就可以選取要傳送的收件者小組 (發佈) 工作清單。 選取小組時，發佈小組可以依階層、依屬性篩選，或是兩者的結合。<br>

![[任務發佈] 的螢幕擷取畫面](media/manage-tasks-app-publish.png)

## <a name="terminology"></a>詞彙

當您流覽階層時，下列字詞就很重要。 團隊將稱為 **節點**。

* **根節點** 是階層中最上層的節點。 在這個範例中，零售通訊是根節點。
* **父節點** 和 **子節點** 是代表兩個連線節點之間關聯的字詞。 在這個範例中，地區01是區域1的子節點。
* 多個子層級稱為 **後代**。 地區01，商店01，商店03，商店07，地區02，地區03則是區域1的所有後代。
* 沒有子節點的節點稱為 **葉節點**。 它們位於階層的底部。
* [**收件者小組**] 是已選取要接收發布的一組特定內容的小組。 它們必須是葉節點。

## <a name="plan-your-hierarchy"></a>規劃階層

在建立定義階層的架構之前，必須先進行一些規劃，並決定您要如何為組織製作圖形。  首先的其中一個優先順序是決定哪些組織群組需要將工作發佈至其他群組。 階層中的每個節點代表一個工作群組或群組群組。

### <a name="permissions-to-publish"></a>發佈許可權

發佈的許可權取決於使用者是否為階層中任何團隊的成員，以及該團隊或團隊的關聯，以及階層中的其他團隊。

> [!NOTE]
> 小組擁有者也被授與發佈許可權。

* 如果使用者是至少一個團隊的成員，且階層中有後代，該使用者就可以發佈到這些後代，而不是他們想要發佈至所有團隊的成員。
* 如果使用者是階層中至少一個團隊的成員，但不是階層中有後代的任何小組成員，該使用者就能查看並從組織中接收已發佈的內容。
* 如果使用者不是階層中任何小組的成員，該使用者就不會看到任何與發佈相關的功能。

### <a name="guidelines"></a>相關

* 每個組織只能套用一個階層檔案。 不過，您可以將組織的不同部分，與單一 CSV 檔案中不同的節點階層結構組成。 例如，Contoso 製藥具有藥房根節點和零售根節點。 兩個根節點都有多列後代，且兩者之間沒有任何交疊。
* 只有葉節點可以是出版物的收件者。 階層中的其他節點對於選取出版物的收件者很有説明。
* 小組只能在階層中表示一次。
* 階層最多可以包含15000節點。 我們打算與客戶合作，為較大的組織增加此限制。

### <a name="example-hierarchy"></a>層次結構範例

例如，在下列階層、召回、通訊和人力資源中，您可以將工作發佈到階層中的每個底層節點 (團隊) ，但東北區域只能將工作發佈至紐約書店和波士頓商店小組。 [範例階層] 可讓 [召回]、[通訊] 和 [人力資源] 群組發佈適用于整個公司的工作，例如 CEO 中的福利資訊或訊息。 東北區域可以發佈工作，例如人事排程、天氣資訊等，只適用于紐約書店與波士頓商店團隊。

![小組階層範例](media/team-targeting-schema-example-new.png)

## <a name="create-your-hierarchy"></a>建立階層

> [!NOTE]
> 本文的其餘部分將討論在向收件者團隊發佈任務的內容中設定小組階層。 請參閱 [在團隊中管理貴組織的 [工作] app](https://docs.microsoft.com/MicrosoftTeams/manage-tasks-app) ，以取得 [任務發佈] （如果啟用的話）。

定義階層的架構是以逗號分隔的值（ (CSV) 檔案）為基礎。 CSV 檔案中的每個資料列都會對應至團隊階層中的一個節點。 每個資料列都包含針對階層中的節點命名的資訊（選擇性地將其連結至團隊），並包含可在支援它之應用程式中用來篩選小組的屬性。

您也可以定義 **bucket**，發佈小組可以用來組織傳送給收件者小組的內容，讓他們更容易查看、排序及專注于相關內容。

### <a name="add-required-columns"></a>新增必要的欄

CSV 檔案必須包含下列三個數據行，並以下列順序從第一欄開始。 若要接收工作，節點必須連結至團隊。

| 欄名稱   | 必要 | 描述   |
----------------|----------|---------------|
| DisplayName    | 是      | 此欄位是節點的名稱。 名稱最多可以有100個字元，且只包含字元 a-z、a-z 及0-9。 節點名稱必須是唯一的。 |
| ParentName    | 是       | 這是父節點的名稱。 您在此處指定的值必須與父節點的 [ **DisplayName** ] 欄位中的值完全相符。 如果您想要新增一個以上的父節點，請使用分號分隔每個父節點名稱 (; ) 。 您最多可以新增25個父節點，且每個父節點名稱最多可以有2500個字元。 只有當父節點是根節點時，節點才能有多個父節點。   <br><br>**重要** 請小心不要建立一個迴圈，層次結構中的上層上方會參照階層較低的子節點。 不支援這種情況。 |
| TeamId        | 是，如果團隊發佈任務或從父節點接收工作       | 這包含您要將節點連結至其中的團隊識別碼。 每個節點必須參照唯一的團隊，所以每個 TeamId 值在階層檔案中可能只會出現一次。 若要取得您想要將節點連結至其中團隊的識別碼，請執行下列 PowerShell 命令： `Get-Team | Export-Csv TeamList.csv` 。 這個命令會列出貴組織中的小組，並包含每個團隊的名稱和識別碼。 找出您要連結的團隊名稱，然後將識別碼複製到此欄位。|

> [!NOTE]
> 如果節點不是根節點或葉節點，而且您不需要團隊成員資格來授與發佈及報告相關的許可權，您可以將 TeamId 留白。 此方法可用於在選擇收件者團隊時新增更多細微性，或在沒有相對應的小組的情況下查看完成報告。

### <a name="add-attribute-columns"></a>新增屬性欄

在您新增三個必要的資料行之後，您可以新增選用的屬性欄。 這些屬性可用來篩選節點，讓您可以更輕鬆地選取您想要發佈任務的專案。 有兩種方式可以定義您的屬性，這要視屬性的值是否相互排斥而定。

|新增屬性的方法|描述 |範例  |
|---|---------|---------|
|如果屬性的值相互排斥，您指定的資料行名稱就會變成屬性的名稱。|每個資料列都可以包含該屬性的一個值，每個屬性欄最多可以有50個唯一值。 每個值最多可以長達100個字元。 當您使用團隊目標階層選取收件者小組時，屬性欄中指定的屬性值集合將會顯示為該屬性的篩選值。|您希望使用者能夠依版面配置篩選儲存。 這個屬性的值是互斥的，因為書店只能有一個版面配置。 <br><br>若要新增屬性來依版面配置篩選儲存，請新增一個名為 [書店版面配置] 的欄。 在這個範例中，Store layout 屬性的值為 Compact、Standard 及大型。
|如果您需要指示屬性的多個值，且這些值不是互斥的，請使用 **AttributeName： UniqueValue** 格式的欄名稱。 <br><br>**重要** 請務必使用英文專用冒號 (： ) 為 unicode，不支援做為屬性欄分隔符號。 |冒號 ( 之前的文字字串： ) 成為屬性的名稱。 所有的資料列都包含相同的文字字串，且在冒號 ( 之前： ) 會分組成 [篩選] 功能表中的某個區段。 冒號後面的每個字串都會成為該節的值。<br><br>每個資料列的值都可以是 0 (零) 或1（針對該屬性）。 值為0表示屬性不會套用至節點，值1表示屬性適用于該節點。|您希望使用者能夠依部門篩選商店。 商店可以有多個部門，所以這個屬性的值不是互相排斥的。<br><br>在這個範例中，我們將新增部門：服裝、部門：電子產品、部門：食物、部門：家用和花園、部門：體育產品是屬性欄。 [部門] 會成為屬性名稱，而且使用者可以透過衣物、電子、食品、家用和花園以及體育用品部門來篩選。|

當您新增屬性欄時，請記住下列事項：

* 您指定的欄名或您在冒號 ( 之前指定的欄名稱： ) 成為屬性的名稱。 此值將會顯示在使用階層的團隊 app 中。
* 您最多可以在層次結構中擁有50屬性欄。
* 資料行名稱最多可以有100個字元，且只包含字元 a-z、a-z 以及0-9 及空格。 欄名必須是唯一的。

### <a name="add-bucket-columns"></a>新增 bucket 欄

您可以新增 bucket 欄來建立桶，該 bucket 是群組，可將任務組織成哪些專案。 每個 bucket 都會在 CSV 檔案中取得自己的欄。 您建立的 bucket 會提供給發佈小組使用。 發佈小組可以使用這些 bucket 來為收件者小組分類工作。 如果小組中不存在某個 bucket，則會在發佈任務時，根據需要建立 bucket。

只要將工作專案集中歸類一次，發佈小組就可以為接收工作清單的數十個、成百上千個或數千個收件者小組預先組織工作清單。 然後，收件者小組可以依 bucket 來排序及篩選其任務，將焦點放在與他們的工作最相關的區域上。

當您新增 [桶] 欄時，請注意下列事項：

* 欄名稱會變成 bucket 的名稱。 您指定的每個 bucket 都會出現在使用階層之小組 app 的 Bucket 清單中。
* 我們建議您不要在 bucket 名稱中包含機密資訊。 目前，發佈團隊在建立後無法透過發佈來移除 bucket。
* 欄名前面必須是 # 號 ( # ) 。 它最多可以包含100個字元，且只能包含字元 a-z、a-z 和0-9。 例如，#Operations 並 #Frozen 商品。
* 階層最多可包含25個 bucket 欄。 我們打算與客戶合作，為較大的組織增加此限制。

### <a name="example"></a>範例

以下是要建立以支援上一個影像所示階層之架構 CSV 檔案的範例。 此架構包含下列專案：

* 三個必要的欄，名為 `TargetName` 、 `ParentName` 和 `TeamId`
* 名為 `Store layout` 、和的三個屬性欄 `Departments:Clothing``Departments:Foods`
* 名為 `Fresh Foods` 、 `Frozen Foods` 和的三個 bucket 欄 `Women's Wear`

`Store layout`屬性具有值，其中包含 `Compact` 、 `Standard` 和 `Large` 。 `Departments`屬性欄可以設定為 `0` (零) 或的值 `1` 。 `Store`版面配置和 `Departments` 屬性不會顯示在上述影像中。 我們在這裡新增這些專案，以協助示範如何將屬性新增至節點專案。 這種情況對於三個桶欄都是一樣的。

```CSV
"TargetName,ParentName,TeamId,Store layout,Departments:Clothing,Departments:Foods,#Fresh Foods,#Frozen Foods,#Women's Wear"
"Recall,,db23e6ba-04a6-412a-95e8-49e5b01943ba,,,,,,"
"Communications,,145399ce-a761-4843-a110-3077249037fc,,,,,,"
"HR,,,,,,,,,,"
"East Regional Office,,,,,,,,,,"
"West Regional Office,,,,,,,,,,"
"Northeast Zone,East Regional Office,,,,,,,,"
"Southeast Zone,East Regional Office,,,,,,,,"
"New York Store,Northeast Zone,e2ba65f6-25e7-488b-b8f0-b8562d5de60a,Large,1,1,,,"
"Boston Store,Northeast Zone,0454f08a-0507-437c-969a-682eb2fae7fc,Standard,1,1,,,"
"Miami Store,Southeast Zone,619d6e4e-5f68-4b36-8e1f-16c98d7396c1,Compact,0,1,,,"
"New Orleans Store,Southeast Zone,6be960b8-72af-4561-a343-9ac4711874eb,Compact,0,1,,,"
"Seattle Store,West Regional Zone,487c0d20-4e55-4dc2-8187-a24c826e0fee,Standard,1,1,,,"
"Los Angeles Store,West Regional Zone,204a1287-2efb-4a8a-88e0-56fbaf5a2389,Large,1,1,,,"
```

## <a name="apply-your-hierarchy"></a>套用您的階層

在架構 CSV 檔案中定義階層之後，您就可以將其上傳至團隊。 若要這樣做，請執行下列命令。 您必須是全域管理員或團隊服務系統管理員，才能執行此步驟。

```powershell
Set-TeamTargetingHierarchy -FilePath "C:\ContosoTeamSchema.csv"
```

### <a name="update-your-hierarchy"></a>更新您的階層

您可以使用與上述相同的 PowerShell 命令，上傳新的階層來取代舊的階層。 每次上傳新的階層時，都會取代先前的階層。

### <a name="check-the-status-of-your-hierarchy"></a>檢查階層的狀態

您可以執行下列命令，以檢查階層上傳的狀態。

```powershell
Get-TeamTargetingHierarchyStatus
```

此命令會傳回下欄欄位：

域|描述
-----|------------
標識號 | 上傳的唯一識別碼。
狀態值 | 上傳狀態。 值包括 **啟動**、 **驗證**、 **成功** 和 **失敗**
ErrorDetails | 詳細資料（如果有上傳錯誤的話）。 如需錯誤詳細資料的詳細資訊，請參閱疑難排解一節。 如果沒有錯誤，此欄位為空白。
LastUpdatedAt | 上次更新檔案的時間戳記和日期。
LastModifiedBy | 上次修改檔案的使用者識別碼。
副檔名 | CSV 的檔案名。

## <a name="remove-your-hierarchy"></a>移除階層

如果您想要立即停用貴組織中所有使用者的 [ **已發佈的清單** ] 索引標籤，您可以移除您的階層。 使用者無法存取 [ **已發佈的清單** ] 索引標籤或 [索引標籤] 上的任何功能。 這包括建立新工作清單以進行發佈、存取草稿清單、發佈、取消發佈及重複清單以及查看報表的功能。 移除階層後，就不會取消發佈先前發佈的工作。 這些工作仍可供收件者團隊完成。

若要移除階層，請執行下列命令。 您必須是系統管理員，才能執行這個步驟。

```powershell
Remove-TeamTargetingHierarchy
```

確認刪除時，狀態訊息仍會顯示先前的架構，但如果再次嘗試刪除，則會傳回物件為 null 的錯誤。

## <a name="create-a-sample-hierarchy"></a>建立範例階層

### <a name="install-the-teams-powershell-module"></a>安裝團隊 PowerShell 模組

> [!IMPORTANT]
> 若要執行此步驟，您必須從 [PowerShell 庫](https://www.powershellgallery.com/packages/MicrosoftTeams/)安裝並使用 [團隊 PowerShell 公用預覽] 模組。 如需如何安裝模組的步驟，請參閱 [安裝團隊 PowerShell](teams-powershell-install.md)。

### <a name="sample-script"></a>範例腳本

下列腳本可用來建立小組，並將 .csv 檔案上傳到您的 Microsoft 團隊租使用者。 如果您已有階層，此腳本會將它取代。

#### <a name="create-teams-for-a-simple-hierarchy"></a>建立適用于簡單階層的團隊

```powershell
$tm1 = New-Team -DisplayName "HQ"
$tm2 = New-Team -DisplayName "North"
$tm3 = New-Team -DisplayName "Store 1"
$tm4 = New-Team -DisplayName "Store 2"
$tm5 = New-Team -DisplayName "South"
$tm6 = New-Team -DisplayName "Store 3"
$tm7 = New-Team -DisplayName "Store 4"
```

#### <a name="use-team-data-to-create-comma-separated-output-displayname-parentname-teamid"></a>使用小組資料來建立以逗號分隔的輸出 (DisplayName、ParentName、TeamId) 

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

#### <a name="save-output-to-a-csv-file-in-the-downloads-folder"></a>將輸出儲存至 [ **下載** ] 資料夾中的 .csv 檔案

```powershell
$csvOutputPath = $env:USERPROFILE + "\downloads\testhierarchy-" + (Get-Date -Format "yyyy-MM-dd-hhmmss") + ".csv" 
$csvOutput | Out-File $csvOutputPath
```

#### <a name="upload-the-hierarchy"></a>上傳階層

```powershell
Set-TeamTargetingHierarchy -FilePath $csvOutputPath
Get-TeamTargetingHierarchyStatus
```

## <a name="troubleshooting"></a>疑難排解

### <a name="how-to-view-error-details"></a>如何查看錯誤詳細資料

您可以執行下列命令，以瞭解導致錯誤的原因，並傳回錯誤詳細資料。

```powershell
(Get-TeamTargetingHierarchyStatus).ErrorDetails.ErrorMessage
```

### <a name="you-receive-an-error-message-when-you-upload-your-schema-csv-file"></a>您上傳架構 CSV 檔案時會收到錯誤訊息

記下錯誤訊息，因為它應該包含疑難排解資訊，以指出無法上傳架構的原因。 根據錯誤訊息中的資訊，查看及編輯您的架構 CSV 檔案，然後再試一次。

### <a name="you-receive-an-error-invalidteamid-error-message-when-you-upload-your-schema-csv-file"></a>當您上傳架構 CSV 檔案時，會收到「錯誤： InvalidTeamId」錯誤訊息

當您嘗試上傳架構 CSV 檔案時，您會收到下列錯誤訊息：

```console
Error: InvalidTeamId
Description: TeamID in row # doesn't match a valid Group ID. Please view our documentation to learn how to get the proper GroupID for each team.
```

請檢查以確定您的架構 CSV 檔案中的小組使用的是正確的 TeamId。 TeamId 應該與支援小組的 Microsoft 365 群組的群組識別碼相同。 您可以在 Microsoft 團隊系統管理中心查詢團隊的群組識別碼。

1. 在 [Microsoft 團隊系統管理中心](https://admin.teams.microsoft.com/)的左導覽中，前往 [**團隊**]  >  **管理團隊**。
2. 如果表格中沒有顯示 [ **群組識別碼** ] 欄，請選取表格右上角的 [ **編輯欄** ]，然後開啟 [ **群組識別碼**]。
3. 在清單中尋找小組，然後找到 [群組識別碼]。

確認您架構 CSV 檔案中的 TeamId 與顯示在 Microsoft 團隊系統管理中心的群組識別碼相符。

## <a name="related-topics"></a>相關主題

* [在團隊中管理貴組織的任務應用程式](manage-tasks-app.md)
* [Teams PowerShell 概觀](teams-powershell-overview.md)

---
title: 設定您的團隊目標階層
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: andfried
search.appverid: MET150
description: 瞭解如何在組織中設定小組階層，以將內容發佈至大型小組。
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 581d67f0083ea8b0e91615a96685f10f4cd64785
ms.sourcegitcommit: 929c050c038a64216e38b0a67569a8f18ad4baf2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/29/2020
ms.locfileid: "43940899"
---
# <a name="set-up-your-team-targeting-hierarchy"></a>設定您的團隊目標階層

> **此功能目前處於私人預覽中。**

若要建立可供貴組織用來將內容發佈至大型小組的小組階層，您必須設定您的團隊目標架構。 架構定義階層中所有團隊的關聯方式，以及可用於篩選團隊的屬性。 建立架構之後，您會將其上傳至團隊，並在整個組織中套用階層。 上傳架構之後，團隊用戶端內的應用程式就可以使用它。 

> [!IMPORTANT]
> 當您在流覽團隊或頻道時，您不會看到團隊的階層。 若要查看團隊階層，您需要使用支援它的應用程式。 初次發行時，只有 [任務] app 支援階層式團隊。 本文的其餘部分將討論在向收件者團隊發佈任務的內容中設定小組階層。 在設定您的團隊目標階層之前，請參閱[在團隊中管理貴組織的任務應用程式](manage-tasks-app.md)，以取得任務發佈的概覽。

以下是在 [團隊] 中的 [工作] 應用程式中代表階層的範例。 在工作清單建立之後，發佈小組的成員就可以選取要傳送（發佈）工作清單的收件者小組。 選取小組時，發佈小組可以依階層、依屬性篩選，或是兩者的結合。<br>

![[任務發佈] 的螢幕擷取畫面](media/manage-tasks-app-publish.png)

## <a name="plan-your-hierarchy"></a>規劃階層

在建立定義階層的架構之前，必須先進行一些規劃，並決定您要如何為組織製作圖形。 這包括決定哪些組織群組需要將工作發佈至其他群組。 階層中的每個節點代表一個工作群組或群組群組。 階層圖底部的節點（沒有子系的那些節點）是可以接收工作的團隊，而其他節點（父）是組織群組，且有許可權可向下發佈任務。 小組只能在階層中表示一次。

例如，在下列階層、召回、零售通訊和人力資源中，您可以將工作發佈到階層中的每個底部節點（團隊），而北美區域只能將工作發佈至紐約書店和波士頓商店團隊。 這個階層允許 [召回]、[零售通訊] 和 [人力資源] 群組發佈適用于整個公司的工作，例如 CEO 中的福利資訊或訊息。 [北方東區域] 可將工作（例如人事排程、天氣資訊等）發佈至紐約書店和波士頓商店團隊。

![小組階層範例](media/team-targeting-schema-example.png)

## <a name="create-your-hierarchy"></a>建立階層

定義階層的架構是以逗號分隔值（CSV）檔案為基礎。 CSV 檔案中的每個資料列都會對應至團隊階層中的一個節點。 每個資料列都包含針對階層中的節點命名的資訊（選擇性地將其連結至團隊），並包含可在支援它之應用程式中用來篩選小組的屬性。

您也可以定義 bucket，發佈小組可以用來組織傳送給收件者小組的內容，讓他們更容易查看、排序及專注于相關內容。

### <a name="add-required-columns"></a>新增必要的欄

CSV 檔案必須包含下列三個數據行，並以下列順序從第一欄開始。 若要接收工作，節點必須連結至團隊。 在私人預覽期間，我們支援500節點。 在啟動時，我們預計預設會支援至少2000節點。 我們打算與客戶合作，為較大的組織增加此限制。

| 欄名稱   | 必要 | 說明   |
----------------|----------|---------------|
| TargetName    | 是      | 這是節點的名稱。 名稱最多可以有100個字元，且只包含字元 a-z、a-z 及0-9。 節點名稱必須是唯一的。 |
| ParentName    | 是       | 這是父節點的名稱。 您在此處指定的值必須與父節點的 TargetName 欄位中的值完全相符。 如果您想要新增一個以上的父節點，請使用分號（;)）分隔每個父節點名稱。 您最多可以新增25個父節點，且每個父節點名稱最多可以有2500個字元。 只有當父節點是根節點時，節點才能有多個父節點。   <br><br>**重要**請小心不要建立一個迴圈，層次結構中的上層上方會參照階層較低的子節點。 不支援這種情況。 |
| TeamID        | 是，如果團隊發佈任務或從父節點接收工作       | 這包含您要將節點連結至其中的團隊識別碼。 如果您希望使用者能從該節點發布，或是您想要讓使用者能夠查看該節點及其後代的報告，就必須連結至該小組（如果該小組位於階層的底部）。 例如，如果您的 [西部] 區域管理員想要查看屬於該區域之節點的任務完成報告。<br><br>如果您只想要在層次結構中群組其他節點的目的中新增節點，您不需要將該節點連結至團隊，也可以將此欄位保留空白。 您可以將每個節點連結到一個團隊。<br>若要取得您想要將節點連結至其中團隊的識別碼，請執行下列 PowerShell 命令： `Get-Team | Export-Csv TeamList.csv`。 這會列出貴組織中的小組，並包含每個團隊的名稱和識別碼。 找出您要連結的團隊名稱，然後將識別碼複製到此欄位。|

### <a name="add-attribute-columns"></a>新增屬性欄

在您新增三個必要的資料行之後，您可以新增選用的屬性欄。 這些屬性可用來篩選節點，讓您可以更輕鬆地選取您想要發佈任務的專案。 有兩種方式可以定義您的屬性，這要視屬性的值是否相互排斥而定。

|新增屬性的方法|說明 |範例  |
|---|---------|---------|
|如果屬性的值相互排斥，您指定的資料行名稱就會變成屬性的名稱。|每個資料列都可以包含該屬性的一個值，而每個值最多可以長達100個字元。 您在屬性欄中指定的屬性值集合，在使用階層的團隊 app 中，將會顯示該屬性的可用篩選值。 每個屬性欄最多可以有50個唯一值。 |您希望使用者能夠依版面配置篩選儲存。 這個屬性的值是互斥的，因為書店只能有一個版面配置。 <br><br>若要新增屬性來依版面配置篩選儲存，請新增一個名為 [書店版面配置] 的欄。 在這個範例中，Store layout 屬性的值為 Compact、Standard 及大型。
|如果您需要指示屬性的多個值，且這些值不是互斥的，請使用**AttributeName： UniqueValue**格式的欄名稱。 |冒號前的文字字串（:)成為屬性的名稱。 冒號前面包含相同文字字串的所有欄（:)會在 [篩選] 功能表中組成一個區段。 冒號後面的每個字串都會成為該節的值。<br><br>每個資料列的值都可以是0（零）或1（表示該屬性）。 值為0表示屬性不會套用至節點，值1表示屬性適用于該節點。|您希望使用者能夠依部門篩選商店。 商店可以有多個部門，所以這個屬性的值不是互相排斥的。<br><br>在這個範例中，我們將新增部門：服裝、部門：電子產品、部門：食物、部門：家用和花園、部門：體育產品是屬性欄。 [部門] 會成為屬性名稱，而且使用者可以透過衣物、電子、食品、家用和花園以及體育用品部門來篩選。|

當您新增屬性欄時，請記住下列事項：

- 您指定的欄名或您在冒號前指定的欄名稱（:)成為屬性的名稱。 此值將會顯示在使用階層的團隊 app 中。
- 資料行名稱最多可以有100個字元，且只包含字元 a-z、a-z 以及0-9 及空格。 欄名必須是唯一的。
- 啟動時，我們打算允許50屬性欄。

### <a name="add-bucket-columns"></a>新增 bucket 欄

您可以新增 bucket 欄來建立桶，該 bucket 是群組，可將任務組織成哪些專案。 每個 bucket 都會在 CSV 檔案中取得自己的欄。 您建立的 bucket 會提供給發佈小組使用。 發佈小組可以使用這些 bucket 來為收件者小組分類工作。 如果小組中不存在某個 bucket，則會在發佈任務時，根據需要建立 bucket。

只要將工作集中分類，發佈小組就可以為接收工作清單的數十個、成百上千個或數千個收件者小組預先組織工作清單。 然後，收件者小組可以依 bucket 來排序及篩選其任務，將焦點放在與他們的工作最相關的區域上。

當您新增 [桶] 欄時，請注意下列事項：

- 欄名稱會變成 bucket 的名稱。 您指定的每個 bucket 都會出現在使用階層之小組 app 的 Bucket 清單中。 我們建議您不要在 bucket 名稱中包含機密資訊。 目前，發佈團隊在建立後無法透過發佈來移除 bucket。
- 欄名前面必須加上井號（#）。 它最多可以包含100個字元，且只能包含字元 a-z、a-z 和0-9。 例如，#Operations 並 #Frozen 商品。
- 啟動時，我們預期會支援25個 bucket 欄。 我們打算與客戶合作，為較大的組織增加此限制。

### <a name="example"></a>範例

以下是要建立以支援上述影像中所示階層之架構 CSV 檔案的範例。 此架構包含下列專案：

- 三個必要的`TargetName`欄`ParentName`，名為、和`TeamID`
- 名為`Store layout`、 `Departments:Clothing`和的三個屬性欄`Departments:Foods`
- 名為`Fresh Foods`、 `Frozen Foods`和的三個 bucket 欄`Womenswear`

`Store layout`屬性具有值，其中包含`Compact`、 `Standard`和`Large`。 `Departments`屬性欄可以設定為值`0` （零）或`1`。 `Store`版面配置和`Departments`屬性不會顯示在上述影像中。 我們在這裡新增這些專案，以協助示範如何將屬性新增至節點專案。 這種情況對於三個桶欄都是一樣的。


| TargetName             | ParentName                      | TeamID                       | 商店版面配置|部門：服裝|部門：食物|#Fresh 食品|#Frozen 食品|#Womenswear|
|------------------------|-------------------------|--------------------------------------|-------------|---|---|---|---|---|
| 上文                 |                         | db23e6ba-04a6-412a-95e8-49e5b01943ba |||||||
| 通訊         |                         | 145399ce-a761-4843-a110-3077249037fc |||||||
| 人力資源                     |                         | b8f7db91-201c-4cf9-9f7e-90a4894ed8e4 |||||||
| 東亞地區 Office   |                         |                                      |||||||
| West 地區辦事處   |                         |                                      |||||||
| 北東區域        | 東亞地區 Office    |                                      |||||||
| 東南部區域        | 東亞地區 Office    |                                      |||||||
| 紐約書店         | 北東區域         | e2ba65f6-25e7-488b-b8f0-b8562d5de60a |大型|1|1||||
| 波士頓商店           | 北東區域         | 0454f08a-0507-437c-969a-682eb2fae7fc |標準|1|1||||
| 邁阿密商店            | 東南部區域         | 619d6e4e-5f68-4b36-8e1f-16c98d7396c1 |簡潔|0|1||||
| 新奧爾良商店      | 東南部區域         | 6be960b8-72af-4561-a343-9ac4711874eb |簡潔|0|1||||
| 西雅圖商店          | West 地區辦事處    | 487c0d20-4e55-4dc2-8187-a24c826e0fee |標準|1|1||||
| 洛杉磯商店      | West 地區辦事處    | 204a1287-2efb-4a8a-88e0-56fbaf5a2389 |大型|1|1||||

## <a name="apply-your-hierarchy"></a>套用您的階層

> [!IMPORTANT]
> 若要執行此步驟，您必須從 PowerShell 測試圖庫安裝並使用最新版本的團隊 PowerShell 模組。 如需如何執行此動作的步驟，請參閱[從 PowerShell 測試圖庫安裝最新的團隊 PowerShell 模組](#install-the-latest-teams-powershell-module-from-the-powershell-test-gallery)。

在架構 CSV 檔案中定義階層之後，您就可以將其上傳至團隊。 若要這樣做，請執行下列命令。 您必須是系統管理員，才能執行這個步驟。 

```powershell
Set-TeamTargetingHierarchy -FilePath "C:\ContosoTeamSchema.csv"
```

## <a name="remove-your-hierarchy"></a>移除階層

> [!IMPORTANT]
> 若要執行此步驟，您必須從 PowerShell 測試圖庫安裝並使用最新版本的團隊 PowerShell 模組。 如需如何執行此動作的步驟，請參閱[從 PowerShell 測試圖庫安裝最新的團隊 PowerShell 模組](#install-the-latest-teams-powershell-module-from-the-powershell-test-gallery)。

如果您想要立即停用貴組織中所有使用者的 [**已發佈的清單**] 索引標籤，您可以移除您的階層。 使用者無法存取 [**已發佈的清單**] 索引標籤或 [索引標籤] 上的任何功能。 這包括建立新工作清單以進行發佈、存取草稿清單、發佈、取消發佈及重複清單以及查看報表的功能。 移除階層後，就不會取消發佈先前發佈的工作。 這些工作仍可供收件者團隊完成。 

若要移除階層，請執行下列命令。 您必須是系統管理員，才能執行這個步驟。 

```powershell
Remove-TeamTargetingHierarchy
```

### <a name="teams-powershell-module"></a>團隊 Powershell 模組

#### <a name="install-the-latest-teams-powershell-module-from-the-powershell-test-gallery"></a>從 PowerShell 測試圖庫安裝最新的團隊 PowerShell 模組

最新公開推出的團隊 PowerShell 模組（目前[1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5)）不支援管理團隊階層。 從 PowerShell 測試圖庫，使用這些步驟來安裝最新版本的團隊 PowerShell 模組（含團隊階層支援）。

> [!NOTE]
> 請勿從 PowerShell 測試圖庫並排安裝團隊 PowerShell 模組與公用 PowerShell 庫中的模組版本。 請依照下列步驟，先從公用 PowerShell 庫中卸載團隊 PowerShell 模組，然後從 PowerShell 測試圖庫安裝最新版本的模組。

1. 關閉所有現有的 PowerShell 會話。
2. 啟動新的 Windows PowerShell 模組實例。
3. 執行下列動作，從公用 PowerShell 庫中卸載團隊 PowerShell 模組：

    ```PowerShell
    Uninstall-Module -Name MicrosoftTeams
    ```

4. 關閉所有現有的 PowerShell 會話。
5. 再次啟動 Windows PowerShell 模組，然後執行下列動作，以將 PowerShell 測試圖庫註冊為受信任的來源：

    ```PowerShell
    Register-PSRepository -Name PSGalleryInt -SourceLocation https://www.poshtestgallery.com/ -InstallationPolicy Trusted
    ```

6. 執行下列動作，從 PowerShell 測試圖庫安裝最新的團隊 PowerShell 模組：

    ```PowerShell
    Install-Module -Name MicrosoftTeams -Repository PSGalleryInt -Force
    ```

7. 執行下列動作，確認已成功安裝 PowerShell 測試圖庫中的最新版本的團隊 PowerShell 模組：

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

#### <a name="update-to-the-latest-version-of-the-teams-powershell-module-from-the-powershell-test-gallery"></a>從 PowerShell 測試圖庫更新到最新版本的團隊 PowerShell 模組

如果您已經從 PowerShell 測試庫安裝團隊 PowerShell 模組，請使用下列步驟更新到最新版本。

1. 關閉所有現有的 PowerShell 會話。
2. 啟動新的 Windows PowerShell 模組實例。
3. 執行下列操作以從 PowerShell 測試圖庫更新目前已安裝的團隊 PowerShell 模組版本：

    ```PowerShell
    Update-Module -Name MicrosoftTeams -Force
    ```

4. 執行下列動作，確認已成功安裝 PowerShell 測試圖庫中的最新版本的團隊 PowerShell 模組：

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

## <a name="troubleshooting"></a>疑難排解

### <a name="you-receive-an-error-message-when-you-upload-your-schema-file"></a>您上傳架構檔案時會收到錯誤訊息

記下錯誤訊息，因為它應該包含疑難排解資訊，以指出無法上傳架構的原因。 根據錯誤訊息中的資訊，查看及編輯您的架構 CSV 檔案，然後再試一次。

## <a name="related-topics"></a>相關主題

- [在團隊中管理貴組織的任務應用程式](manage-tasks-app.md)

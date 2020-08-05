---
title: 在團隊系統管理中心管理稱讚應用程式
author: CaitlynZawideh
ms.author: t-cazaw
manager: serdars
audience: admin
ms.topic: article
ms.service: msteams
localization_priority: Normal
description: 瞭解 Microsoft 團隊系統管理中心的稱讚應用程式中的系統管理設定
ms.openlocfilehash: a61b4236a3c1378cbe4134833ad0f3fcd5b1651c
ms.sourcegitcommit: ab094058e3ffa974527fce8a331dad609ac19609
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/04/2020
ms.locfileid: "46552829"
---
# <a name="manage-the-praise-app-in-the-microsoft-teams-admin-center"></a>在 Microsoft 團隊系統管理中心中管理稱讚應用程式

Microsoft 團隊中的稱讚應用程式可協助使用者向組織或教室的成員顯示感謝。 您可以選擇一組徽章以供選擇，以及建立您自己徽章的選項，稱讚旨在協助您認識到小組使用者所做的大量工作（從教育者到第一行員工）。

系統管理員可以控制哪些徽章可供其組織從 [小組] 系統管理中心中取得。 在左側導覽中，選取 [**團隊 app] > [管理 app**]。 在租使用者的 [[應用程式目錄](https://docs.microsoft.com/microsoftteams/manage-apps#view-apps-in-your-tenant-app-catalog)] 中開啟稱讚，然後移至 [**設定**]。

## <a name="use-built-in-badge-sets"></a>使用內建徽章集

內建集是 Microsoft 針對稱讚應用程式設計的徽章集合。 系統管理員無法編輯這些集合。 預設徽章集已啟用，且可在稱讚 app 中使用。 若要變更預設集或任何徽章集的可用性，請將對應的切換開關切換為 [開啟] 或 [關閉]。 

<a name="default-badges"></br></a>

### <a name="default-badges"></a>預設徽章

預設徽章集是專門用來協助團隊使用者認識其同事，以進行工作的上方和結尾。

![預覽預設徽章集](media/default-set-praise.png)

<a name="sel-edu-badges"></br></a>

### <a name="social-and-emotional-learning-badges-for-education"></a>教育版社交和激動人心的學習徽章

教學課程可以辨識個別學生的社交與激動人心的學習 (SEL) 成就與行為，以及可說明這些概念的徽章。

![針對教育版社交與激動人心的學習徽章預覽](media/sel-edu-set-praise.png)

<a name="create-your-own-badges"></br></a>

## <a name="create-your-own-badges"></a>建立您自己的徽章

將**自訂徽章**切換開關切換至 [開啟]，然後選取 [**建立自訂徽章**]。 在該處，您可以在側邊面板中設計自訂徽章。

1. 輸入徽章名稱。 這是使用者傳送稱讚時，會出現在徽章上的名稱。

2. 設定您的徽章色彩。 若要設定徽章的文字和背景色彩，您必須以十六進位) 值的形式輸入 (的色彩。

   > [!TIP]
   > 如果您是十六進位值的新使用者，本文將說明如何使用它們的[快速簡介](#hex-colors-intro)。

3. 上傳徽章影像。 接受的檔案類型是。PNG. 檔案必須小於25kb。
![標題為 [背景]、[文字] 和 [圖像] 欄位的徽章](media/praise-app-badge-fields.png)

4. 當地語系化徽章名稱：在 [**當地語系化徽章名稱**] 底下，選取 [**新增**]。 從下拉式清單中選取所要的地區設定。 然後以指定的語言輸入徽章名稱。

5. 從特定地區設定中排除徽章：在 [**從這些區域設定中排除徽章**] 底下，選取 [**新增**]。 從下拉式清單中選取您要排除的地區。

6. 選取 **[** 套用]。 您的新徽章現在會出現在 [自訂徽章] 表格中。

> [!NOTE]
> 如果跳過步驟4和5，徽章將會成為所有地區設定的預設語言。
>
> 當您完成變更徽章選取專案時，請務必選取 [**提交**]。 可能需要幾個小時，才能讓您的組織使用這些變更。

<a name="hex-colors-intro"></br></a>

## <a name="specify-colors-with-hex-values"></a>指定含十六進位值的色彩

十六進位色彩值是六個十六進位數位的字串，代表紅色 (RR 的亮度) 、綠色 (GG) ，以及從00到 FF 的特定色彩中的藍色 (BB) 。 當您將三個顏色的值放在一起時，會得到十六進位值： #RRGGBB

例如，紅色的十六進位值是 #FF0000，因為紅色是設定為最高可能值、FF、綠色和藍色，每個值都是以最低的可能值00來設定。

若要探索不同的色彩及其十六進位值，請參閱[Bing 色彩選擇器](https://www.bing.com/search?q=color+picker)。

以下是可供您快速入門的範例色彩清單：

|顏色  |十六進位值|
|-------|---------|
|![十六進位色彩 #FF6666](media/hexColor1.png)|  #FF6666   |
|![十六進位色彩 #7FFFD4](media/hexColor2.png)|  #7FFFD4   |
|![十六進位色彩 #FF75F0](media/hexColor3.png)|  #FF75F0   |
|![十六進位色彩 #00BFFF](media/hexColor4.png)|  #00BFFF   |
|![十六進位色彩 #800080](media/hexColor5.png)|  #800080   |
|![十六進位色彩 #000000](media/hexColor6.png)|  #000000   |

<a name="best-practices"></br></a>

## <a name="best-practices-for-creating-custom-badges"></a>建立自訂徽章的最佳做法

**一次提交您的所有徽章。** 由於要處理新徽章需要一段時間，因此最好在提交前先將所有自訂徽章新增至表格。

**選擇色彩時，請記住協助工具。** 某些色彩比其他色彩更好。  在文字與背景色彩之間建立對比，讓徽章名稱易於閱讀。 例如，如果您選擇深背景色彩，請選擇淺文字色彩。

**選取影像時，請記住徽章尺寸。** 為了獲得最佳品質，建議您上傳216x216 圖元的影像檔。 避免拉伸或扭曲圖像，以符合這些尺寸。

**如果您的徽章影像不是矩形，請將影像設成透明。** 您必須先執行此動作，才能將影像檔案上傳到稱讚。

![左側：含非透明圖像的徽章，右側：含有透明圖像的徽章](media/praise-app-best-practices.png)

## <a name="badge-set-assets"></a>徽章集資產

內建徽章集無法修改，因此當啟用內建集時，集合中的所有徽章都會新增至稱讚應用程式。 如果您想要從內建集新增特定徽章，並留下其他人，請重新建立您要用來做為自訂徽章的徽章。 您可以下載徽章圖像，並從下表中的內建集尋找徽章的文字和背景色彩。

### <a name="default-badges-assets"></a>預設徽章資產

</br>

|徽章名稱     |影像檔  |文字色彩 | 背景色彩 |
|---------------|------------|---------- |--------|
|Achiever       |[Achiever PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/achiever-badge.png)|#D36E70    |#E3F4FC|
|主要        |[[超想] PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/awesome-badge.png>Awesome.PNG)</a>|#8283B2    |#D1EFF2|
|指導          |[[教練] PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/coach-badge.png)</a>|#6AA55A    |#DBF1D6|
|Courage        |[Courage PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/courage-badge.png)</a>|#DC5041    |#FCF6C8|
|心       |[創造性的 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/creative-badge.png) |#CF9D50    |#FCF6C8|
|兩端      |[包含 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/inclusive-badge.png)</a>|#3C77BB    |#E2F4FC|
|類型心形     |[類型心形（PNG）](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/kind-heart-badge.png)</a>|#D36D6E    |#F4DEDE|
|領導     |[[領導] PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/leadership.pn)|#419098    |#D2EAEC|
|Optimism       |[Optimism PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/optimism-badge.png)</a>|#D8338C    |#F4DDDE|
|問題規劃求解 |[問題規劃求解 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/problem-solver-badge.png)|#B8916E    |#CBDADF|
|小組玩家    |[小組玩家 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/team-player-badge.png)|#8B8DC0    |#F4EEC0|
|謝謝      |[答謝 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/thank-you-badge.png)|#469CA4    |#BACCB6|

</br>

### <a name="social-and-emotional-learning-badges-for-education-assets"></a>教育資產的社交及情緒學習徽章

</br>

|徽章名稱        |影像檔  |文字色彩 | 背景色彩 |
|------------------|------------|---------- |--------|
|迅     |[通訊 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/communication-badge.png)|#FFFFFF    |#173B65|
|重要思維 |[[重要思維] PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/critical-thinking-badge.png)|#FFFFFF    |#084D26|
|好奇心         |[好奇心 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/curiosity-badge.png)|#FFFFFF    |#008078|
|理解           |[理解 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/empathy-badge.png)|#FFFFFF    |#650B35|
|目標追求      |[目標追求 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/goal-pursuit-badge.png)|#FFFFFF    |#006F95|
|推動        |[動機 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/motivation-badge.png)|#FFFFFF    |#C52127|
|存留       |[暫留 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/persistence-badge.png)|#FFFFFF    |#167D3E|
|互相           |[考慮 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/respect-badge.png)|#FFFFFF    |#8251A0|
|領域    |[責任 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/responsibility-badge.png)|#FFFFFF    |#B05DA3|
|自我意識    |[自我感知 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/self-awareness-badge.png)|#FFFFFF    |#1680E5|
|自我管理   |[自我管理 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/self-management-badge.png)|#FFFFFF    |#4C144D|
|Thoughtfulness    |[Thoughtfulness PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/thoughtfulness-badge.png)|#FFFFFF    |#EE4086|

---
title: Lync Server 2013：瞭解由最佳做法分析工具所建立的報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding reports created by Best Practices Analyzer
ms:assetid: 1386dd6c-7f3e-4da9-905b-cef1468bf14a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591344(v=OCS.15)
ms:contentKeyID: 48183471
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2262c490d84ec6f93ff395a9c8ec38d81c82e7de
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744793"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-reports-created-by-best-practices-analyzer-in-lync-server-2013"></a>瞭解 Lync Server 2013 中由最佳做法分析工具所建立的報告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-10_

最佳做法分析工具提供多個組織類型，以協助分析及問題的解決。 最佳做法分析程式會找出錯誤、警告及其他資訊等問題。

<div>

## <a name="reports"></a>有關

您可以透過查看下列每個報告來存取掃描結果：

  - **清單報告**   清單報告是依特定準則來組織。 您可以依類別、嚴重性或問題來排列結果。 例如，如果您依班級組織結果，則會將與主管相關的問題包含在報告的 [控制器] 區段底下。 您可以查看所有問題，或只是資訊性專案。 您可以搜尋特定專案（例如 [記憶體]）的清單報表。 您也可以列印報表或將其匯出。

  - **樹狀報表**   樹狀報表是由用來執行掃描的規則，以及在執行掃描時指定的其他選項所組成。 例如，與測試拓撲規則相關的問題會包含在報告的 [測試拓撲] 區段底下。 您可以查看所有問題的詳細資料，或只查看問題的摘要。 您可以搜尋樹狀報表中的特定專案，例如 [記憶體]。 您也可以列印報表或將其匯出。

  - ****    其他報表中的其他報表專案，包括掃描中所包含的執行時間記錄。 您可以在其他報表中搜尋特定專案的專案，例如 [記憶體]。 您也可以列印報表或將其匯出。

</div>

<div>

## <a name="issues"></a>存在

最佳做法分析程式所產生的報告，會指出在您的環境中發現的特定問題，包括下列類型的問題：

  - **錯誤**   需要您在環境中變更的重要問題。 例如，如果未安裝 Lync Server 2013 核心元件，則會記錄錯誤。
    
    在報表中，會以紅色 X 符號來標識類別為錯誤的問題。 錯誤會顯示在 [**清單報告**] 視圖的 [**所有問題**] 索引標籤上，以及 [**詳細視圖**] 索引標籤和 [**樹狀報表**] 視圖的 [**摘要視圖**] 索引標籤上。 如果您不想在報表中看到特定錯誤，您可以指定不會針對單一實例或報表中該錯誤的所有實例顯示錯誤。 接著，除非您變更設定並指定要在報表中顯示錯誤，否則會在 [**其他報表**] 視圖的 [**隱藏專案**] 索引標籤上顯示錯誤。

  - ****    與最佳做法實現不一致的警告問題。 這可能會表示您的環境需要變更，也可能不需要。 這個問題可能是您不需要變更之特定設定的已知問題。 例如，未在伺服器上啟動的服務會記錄為警告。
    
    在報告中，會以三角形黃色警告符號來標識分類為警告的問題。 警告會顯示在 [**清單報告**] 視圖的 [**所有問題**] 索引標籤上，以及 [**詳細視圖**] 索引標籤和 [**樹狀報表**] 視圖的 [**摘要視圖**] 索引標籤上。 如果您不想在報表中看到特定錯誤，您可以指定不會針對單一實例或報表中該錯誤的所有實例顯示錯誤。 然後，除非您變更設定並指定要在報表中顯示警告，否則將會在 [**其他報表**] 視圖的 [**隱藏專案**] 索引標籤上顯示警告。

  - **資訊**   包括所有未分類為錯誤或警告的問題。 例如，Active Directory 網域服務中的 Lync Server 2013 標準版 server 物件數會分類為資訊問題。
    
    資訊問題會顯示在 [**清單報告**] 視圖的 [**所有問題**] 索引標籤上，以及 [**樹狀報表**] 視圖的 [**詳細**資料] 索引標籤上。

Lync Server 2013，最佳做法分析工具不會變更您的環境以解決問題。 [掃描] 只會偵測到可能的問題，並提供報告，其中包含如何解決每個問題的相關資訊。

如果您按一下某個問題，則會針對特定問題顯示說明及一些選項。 接著，您可以執行下列任何一項操作：

  - 尋找問題的詳細資訊，以及解決問題的方法。

  - 停止顯示報表中的問題：
    
      - 停止顯示所選實例的問題。
    
      - 停止顯示該問題所有實例的相關問題。
    
    若要查看您已停止顯示在報表中的問題，請移至 [**其他報表**] 視圖的 [**隱藏的專案**] 索引標籤。 您可以在這裡指定再次開始顯示報表中的問題。

如需解決特定問題的詳細資料，請參閱[在 Lync Server 2013 中分析及解決最佳做法分析程式所識別的問題](lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>


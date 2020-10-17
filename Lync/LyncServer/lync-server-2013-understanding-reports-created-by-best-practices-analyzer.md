---
title: Lync Server 2013：瞭解最佳做法分析器所建立的報告
description: Lync Server 2013：瞭解最佳做法分析器所建立的報告。
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
ms.openlocfilehash: 5fbb84cdffe6e6e6f079c2d72aba4799f5538776
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542369"
---
# <a name="understanding-reports-created-by-best-practices-analyzer-in-lync-server-2013"></a>瞭解 Lync Server 2013 中的最佳做法分析程式所建立的報告

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-10_

Best Practices Analyzer 提供多種報告類型，有助於分析及解決問題。Best Practices Analyzer 會識別錯誤、警告及其他資訊等問題。

<div>

## <a name="reports"></a>報告

您可以檢視下列每個報告來存取掃描結果：

  - **清單報告**    清單報表依特定準則進行組織。 您可以依類別、嚴重性或問題來排列結果。 例如，如果您依類別來組織結果，與 Director 相關的問題就會包含在報告的 Director 區段底下。 您可以檢視所有問題，或只檢視參考項目。 您可以在清單報告中搜尋特定項目，例如記憶體。 您也可以列印報告或將它匯出。

  - **樹報表**    樹狀報表是以執行掃描時所用的規則來組織，另一種是在執行掃描時指定的其他選項。 例如，與測試拓撲規則相關的問題會包含在報告的測試拓撲區段底下。 您可以檢視所有問題的詳細資訊，或只檢視問題的摘要。 您可以在樹狀報告中搜尋特定項目，例如記憶體。 您也可以列印報告或將它匯出。

  - **其他報告**    其他報告中的專案包含掃描中所包含之工作的執行時間記錄。 您可以在其他報告中搜尋特定項目，例如記憶體。 您也可以列印報告或將它匯出。

</div>

<div>

## <a name="issues"></a>問題

Best Practices Analyzer 所產生的報告會指出在掃描環境期間識別的特定問題，包括下列類型的問題：

  - **錯誤**    需要您在環境中進行變更的重大問題。 例如，如果未安裝 Lync Server 2013 核心元件，則會記錄錯誤。

    報告中會以紅色 X 符號來識別分類為錯誤的問題。錯誤會顯示在 [清單報告]**** 檢視的 [所有問題]**** 索引標籤上，以及 [樹狀報告]**** 檢視的 [詳細檢視]**** 索引標籤或 [摘要檢視]**** 索引標籤上。如果您不想在報告中看到特定錯誤，可以指定不要在報告中顯示該錯誤的單一執行個體或所有執行個體。該錯誤就只會顯示在 [其他報告]**** 檢視的 [隱藏項目]**** 索引標籤上，除非您變更設定，並指定在報告中顯示該錯誤。

  - **警告**    與最佳作法的實施不一致的問題。 這不一定表示需要在環境中進行變更。 此問題可能是不需要變更之特定設定的已知問題。 例如，未在伺服器上啟動的服務就會記錄為警告。

    報告中會以黃色三角形的警告符號來識別分類為警告的問題。警告會顯示在 [清單報告]**** 檢視的 [所有問題]**** 索引標籤上，以及 [樹狀報告]**** 檢視的 [詳細檢視]**** 索引標籤或 [摘要檢視]**** 索引標籤上。如果您不想在報告中看到特定錯誤，可以指定不要在報告中顯示該錯誤的單一執行個體或所有執行個體。該警告就只會顯示在 [其他報告]**** 檢視的 [隱藏項目]**** 索引標籤上，除非您變更設定，並指定在報告中顯示該警告。

  - **資訊**    包括所有未分類為錯誤或警告的問題。 例如，Active Directory 網域服務中的 Lync Server 2013 Standard Edition server 物件數目會分類為資訊問題。

    資訊問題會顯示在 [清單報告]**** 檢視的 [所有問題]**** 索引標籤上，以及 [樹狀報告]**** 檢視的 [詳細檢視] **** 索引標籤上。

Lync Server 2013，最佳做法分析器不會變更您的環境以解決問題。 掃描只會偵測潛在問題，並提供包含如何解決各問題的相關資訊報告。

當您按一下問題，就會顯示特定問題的說明和某些選項。然後，您可以執行下列任何動作：

  - 尋找有關該問題以及如何解決的更多詳細資訊。

  - 停止在報告中顯示問題：

      - 停止顯示選定執行個體的問題。

      - 停止顯示該問題所有執行個體的問題。

    若要顯示您已在報告中停止顯示的問題，請前往 [其他報告]**** 檢視的 [隱藏項目]**** 索引標籤。您可以從那裡指定在報告中重新開始顯示問題。

如需解決特定問題的詳細資訊，請參閱 [分析和解決 Lync Server 2013 中的最佳做法分析程式所識別的問題](lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

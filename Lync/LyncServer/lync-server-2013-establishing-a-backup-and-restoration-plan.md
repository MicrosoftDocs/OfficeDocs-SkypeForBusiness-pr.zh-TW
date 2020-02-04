---
title: Lync Server 2013：建立備份和還原方案
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Establishing a backup and restoration plan
ms:assetid: 9f562ef1-3804-41e2-b3e4-d45b2e8c63c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202183(v=OCS.15)
ms:contentKeyID: 51541499
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cee1c4571dafa4e513f42613de13205ecec9de42
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735254"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="establishing-a-backup-and-restoration-plan-for-lync-server-2013"></a>建立 Lync Server 2013 的備份與還原方案

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-17_

建立備份和還原方案涉及下列步驟：

  - 開發規劃。

  - 實施方案。

  - 維護方案。

<div>

## <a name="developing-a-backup-and-restoration-plan"></a>開發備份與還原方案

在您開發 Lync Server 的備份和還原策略之後，請使用它來記錄詳細的備份和還原方案。 您的計畫應該清楚地傳達備份資料和設定的優先順序與需求。 您可以使用此資訊來[建立 Lync server 2013 的備份與還原策略](lync-server-2013-establishing-a-backup-and-restoration-strategy.md)，以及[Lync server 2013 備份與還原工作](lync-server-2013-backup-and-restoration-worksheets.md)表中的工作表，以協助您的戰略檔。 您的規劃也應該包含決定何時及如何還原服務的準則。

當您開發方案時，您必須考慮下列事項，並考慮下列事項：

  - 您將在新硬體上復原伺服器的方式。

  - 您將如何復原需要在多個商務區域或部門中進行動作的服務。

  - 您可以如何快速取得待命伺服器。

  - 使用您的策略來復原所需的時間。 考慮貴組織對恢復時間目標（RTO）的需求。

修改本主題中的備份和還原程式，視需要新增及刪除程式，以反映部署中的伺服器和元件。 您也可以在適當的程式中新增適當的詳細資料（例如備份排程），以確保資訊不會被忽略。

<div>


> [!NOTE]  
> 最好的做法是建立盡可能多步驟的腳本，以協助確保程式的品質與 reproducibility。



</div>

在您的計畫中，指定負責仲裁者案的人員，負責測試和驗證任何新程式或工具的人員，以及必須核准方案和相關程式的任何變更。

若要確保您的備份和還原方案完全符合所有已建立的目標與優先順序，請在實施方案之前，先核准貴組織中適當的商業決策者和技術決策者。

</div>

<div>

## <a name="implementing-the-backup-and-restoration-plan"></a>實施備份和還原方案

執行備份和還原方案需要執行下列步驟：

  - 測試和驗證方案。

  - 溝通方案。

  - 驗證備份和還原作業。

<div>

## <a name="testing-and-validating-the-plan"></a>測試和驗證方案

這裡所述的程式已在實驗室環境中測試和驗證。 若要確保這些或任何其他程式可在您的環境中運作，您應該測試並驗證您想要實現的每個程式。 在提交您的最終核准方案之前，請先完成測試和驗證。

</div>

<div>

## <a name="communicating-the-plan"></a>溝通方案

您的備份和還原方案應該清楚描述執行程式的人員，以及執行程式的逐步指示。 您應該確定任何負責備份和還原之層面的人都瞭解規劃、其實施方式，以及角色的作用。 這包括下列各項的實現需求：

  - [池] 和 [伺服器備份]。

  - 還原服務。

**池和伺服器備份**

備份與還原方案應包含完成備份程式所需的所有資訊。 將主要資訊傳達給負責的小組成員，包括下列各項：

  - 負責備份每個伺服器的小組或人員（指定為個人或角色）。

  - 備份每個伺服器的特定排程。

  - 每個資料類型（設定、資料庫及檔案共用）的備份位置。

  - 要使用的備份程式，包括完成每個程式所需的工具。

  - 完成備份所需的資訊，如[Lync Server 2013 的備份和還原工作表](lync-server-2013-backup-and-restoration-worksheets.md)中所述。

  - 驗證方法可用來協助確保資料和設定已適當備份且可供還原，這可能包括週期性審核及測試還原。

**還原服務**

備份與還原方案應包含還原服務所需的所有資訊，以防一或多個伺服器遇到使服務無法使用的損失。 將主要資訊傳達給負責的小組成員，包括下列各項：

  - 小組或人員（指定為個人或角色）負責決定何時需要還原服務，以及用來還原服務的程式小組或人員，以及負責執行每個程式的程式。還原案例。

  - 決定哪一種還原程式最適合特定情況的準則。

  - 在每個還原案例中，還原服務與復原時間目標（RTO）的時間估計。

  - 要使用的還原程式，包括完成每個程式所需的工具。

  - 還原資料和設定所需的資訊。 在[Lync Server 2013 的備份與還原工作表](lync-server-2013-backup-and-restoration-worksheets.md)中提供工作表。

</div>

<div>

## <a name="validating-backup-and-restoration-operations"></a>驗證備份和還原作業

在您的生產環境中，以指定的間隔（如備份與還原方案中所述）完成初始備份工作之後，您應該確認下列事項：

  - 根據需要進行備份。

  - 已備份的資料和設定可供存取。

  - 您可以在備份和還原方案中指定的恢復時間目標（RTO）時間內執行還原程式，結果就能滿足所有業務需求。

  - 備份工作表已完成並驗證，且儲存在安全的位置。 這些工作表是在[Lync Server 2013 的備份與還原工作表](lync-server-2013-backup-and-restoration-worksheets.md)中提供。

  - 還原程式已經過測試和驗證，如您在備份和還原方案中所指定的那樣正常運作。

</div>

</div>

<div>

## <a name="maintaining-the-backup-and-restoration-plan"></a>維護備份和還原方案

Lync Server 拓撲是與您的組織變更的動態環境。 重新評估您的組織變更的備份和還原方案，並定期進行審查，以確保它繼續符合您的企業需求。

</div>

</div>

<span> </span>

</div>

</div>

</div>


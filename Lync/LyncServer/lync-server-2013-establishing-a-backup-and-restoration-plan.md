---
title: Lync Server 2013：建立備份與還原計劃
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
ms.openlocfilehash: 64d9842ccb9d83fb7ce81c326008e36722e45764
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514220"
---
# <a name="establishing-a-backup-and-restoration-plan-for-lync-server-2013"></a>建立 Lync Server 2013 的備份與還原方案

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-17_

建立備份與還原計劃包含下列步驟：

  - 開發計畫。

  - 實施計畫。

  - 維護計畫。

<div>

## <a name="developing-a-backup-and-restoration-plan"></a>開發備份與還原計劃

在您開發 Lync Server 的備份與還原策略後，請使用它來記錄詳細的備份與還原計劃。 您的計畫應明確傳達備份資料和設定的優先順序和需求。 您可以使用此資訊來 [建立 lync server 2013 的備份與還原策略](lync-server-2013-establishing-a-backup-and-restoration-strategy.md) ，以及 [Lync server 2013 備份與還原工作](lync-server-2013-backup-and-restoration-worksheets.md) 表中的工作表，以協助您的策略的檔。 您的計畫還應該包含決定何時及如何還原服務的準則。

當您開發計畫時，您必須考慮下列各項，並加以考慮：

  - 如何在新的硬體上復原伺服器。

  - 在多個商務區域或部門中，您將如何復原需要動作的服務。

  - 您可以如何快速取得待命伺服器。

  - 使用您的策略復原所需的時間。 請考慮貴組織對於恢復時間目標 (RTO) 的需求。

修改本主題中的備份與還原程式，以適當的方式新增及刪除程式，以反映部署中的伺服器和元件。 您也可以將適當的詳細資料（例如備份排程）新增至適當的程式，以確保資訊不會被忽視。

<div>


> [!NOTE]  
> 最佳作法是盡可能建立腳本，以協助確保程式的品質和 reproducibility。



</div>

在您的計畫中，指定負責檢查方案的人員、負責測試及驗證任何新程式或工具的人員，以及必須核准方案和相關程式的任何變更的人員。

若要確定您的備份和還原方案完全符合所有既定的目標和優先順序，請在實施計畫之前，先核准組織中適當的 business 決策者和技術決策者。

</div>

<div>

## <a name="implementing-the-backup-and-restoration-plan"></a>實施備份與還原計劃

執行備份與還原計劃需要下列步驟：

  - 測試及驗證計畫。

  - 交流計畫。

  - 驗證備份及還原作業。

<div>

## <a name="testing-and-validating-the-plan"></a>測試及驗證計畫

這裡所述的程式已在實驗室環境中測試及驗證。 若要確定這些或任何其他程式在您的環境中運作，您應該測試及驗證您要執行的每個程式。 在您提交最終核准的計畫之前，請先完成測試和驗證。

</div>

<div>

## <a name="communicating-the-plan"></a>交流計畫

您的備份和還原計劃應該清楚地說明執行程式的執行者及執行程式的逐步指示。 您應確定負責備份與還原之任何方面的人員瞭解計畫、其實施方式及其角色。 這包括下列各項的執行需求：

  - 集區和伺服器備份。

  - 還原服務。

**集區和伺服器備份**

備份與還原計劃應包含在日常執行備份程式時所需的所有資訊。 要傳遞給負責的小組成員的主要資訊如下：

  - 小組或個人 (會指定為個人或角色) 負責備份每台伺服器。

  - 備份每一部伺服器的特定計劃。

  - 每個資料類型的備份位置 (設定、資料庫及檔案共用) 。

  - 要使用的備份程式，包含完成每個程式所需的工具。

  - 完成備份所需的資訊，如 [Lync Server 2013 的備份與還原工作表](lync-server-2013-backup-and-restoration-worksheets.md)中所述。

  - 用來協助確保資料和設定進行適當備份及可供還原使用的驗證方法，其中包括週期性審計及測試還原。

**服務的還原**

備份與還原計劃應包含還原服務時所需的所有資訊，以防一或多部伺服器遇到使服務無法使用的遺失。 要傳遞給負責的小組成員的主要資訊如下：

  - 小組或個人 (會指定為個人或角色) ，負責決定何時需要還原服務，以及用來還原服務的程式，也就是負責針對每個還原案例執行程式的小組或人員。

  - 決定哪些還原程式最適合特定狀況的準則。

  - 還原服務和恢復時間目標的時間估計 (每個還原案例中的 RTO) 。

  - 要使用的還原程式，包含完成每個程式所需的工具。

  - 還原資料及設定所需的資訊。 工作表會在 [Lync Server 2013 的備份與還原工作表](lync-server-2013-backup-and-restoration-worksheets.md)中提供。

</div>

<div>

## <a name="validating-backup-and-restoration-operations"></a>驗證備份及還原作業

在實際執行環境中和指定的間隔完成初始備份工作之後，您應該在 (備份與還原計劃) 中，確認下列各項：

  - 備份會在必要時進行。

  - 備份的資料和設定可供存取。

  - 您可以在復原時間目標中執行還原程式， (備份與還原計劃中所指定的 RTO) 時間，以及結果是否符合所有業務需求。

  - 備份工作表已完成並驗證，且儲存在安全的位置。 在 [Lync Server 2013 的備份與還原工作表](lync-server-2013-backup-and-restoration-worksheets.md)中提供這些工作表。

  - 還原程式已經過測試及驗證，可如您的備份和還原計劃中所指定的那樣運作。

</div>

</div>

<div>

## <a name="maintaining-the-backup-and-restoration-plan"></a>維護備份與還原計劃

Lync Server 拓撲是隨組織變更的動態環境。 在您的組織變更時重新評估備份與還原方案，並定期複查，以確保它繼續符合您的業務需求。

</div>

</div>

<span> </span>

</div>

</div>

</div>


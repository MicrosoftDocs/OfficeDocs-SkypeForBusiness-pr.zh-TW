---
title: Lync Server 2013： 建立備份和還原規劃
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
ms.openlocfilehash: c0edc085ae57c8d261111726768b8ca3309c87dd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137332"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="establishing-a-backup-and-restoration-plan-for-lync-server-2013"></a>建立 Lync Server 2013 的備份和還原規劃

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-17_

建立備份和還原規劃包括下列步驟：

  - 研擬規劃。

  - 實作計劃。

  - 維護計劃。

<div>

## <a name="developing-a-backup-and-restoration-plan"></a>研擬備份和還原規劃

Lync Server 的開發您的備份和還原策略之後，請用它來詳細的備份和還原規劃的文件。 優先順序及備份資料和設定的需求，應該清楚地傳達您的計劃。 您可以使用中[建立 Lync Server 2013 的備份和還原策略](lync-server-2013-establishing-a-backup-and-restoration-strategy.md)的資訊和[Lync Server 2013 的備份及還原工作表](lync-server-2013-backup-and-restoration-worksheets.md)中的工作表，以利策略的說明文件。 您的計劃應該也包含準則決定何時及如何還原服務。

當您開發您的計劃，您必須考量，並考慮，下列：

  - 如何還原在新硬體上的伺服器。

  - 如何還原需涉及多個業務地區或部門的服務。

  - 您如何可以快速取得備用伺服器。

  - 復原使用您策略所需的時間。 請考慮您的組織需求的復原時間目標 (RTO)。

修改本主題中，新增和刪除視，以反映伺服器和元件在部署中的程序中的備份和還原程序。 您也可以新增適當的詳細資訊，例如備份排程，以適當的程序，以確保資訊不會被忽略。

<div>


> [!NOTE]  
> 它是很好的作法盡可能，以協助確保品質和腳本程序建立多個步驟的指令碼。



</div>

在您的計劃中，指定誰負責檢閱計劃，誰負責進行測試及驗證的任何新的程序或工具，以及使用者必須核准規劃和相關程序的任何變更。

若要確認您的備份和還原規劃完全符合所有制定的目標和優先順序，實施規劃前，貴組織中取得適當的商務決策者和技術決策者的核准。

</div>

<div>

## <a name="implementing-the-backup-and-restoration-plan"></a>實施備份和還原規劃

實作備份和還原規劃需要下列步驟：

  - 測試及驗證計劃。

  - 規劃的傳達。

  - 驗證備份與還原作業。

<div>

## <a name="testing-and-validating-the-plan"></a>測試及驗證計劃

此處所述的程序已經測試並在實驗室環境中進行驗證。 若要確定在您的環境中這些或任何其他程序運作，您應測試及驗證您想要實作每項程序。 完成測試和驗證才能提交您的計劃進行最終核准。

</div>

<div>

## <a name="communicating-the-plan"></a>規劃的傳達

您的備份和還原規劃應該清楚說明人員實作程序和 save 程序的逐步指示。 您應該要確定所有人負責備份及還原的任何層面瞭解規劃、 它的方式實作，以及其角色是。 這包括下列所有實作需求：

  - 集區和伺服器備份。

  - 還原服務。

**集區和伺服器備份**

備份和還原規劃應包含完成持續的備份程序所需的所有資訊。 主要的資訊，以傳達給負責小組成員包含下列特性：

  - 小組或人員 （指定為個人或職位） 負責備份各伺服器。

  - 備份每個伺服器的特定排程。

  - 每種類型的資料 （設定、 資料庫及檔案共用） 的備份位置。

  - 備份程序，以使用，包括完成每項程序所需的工具。

  - 完整備份，[備份及還原 Lync Server 2013 的工作表](lync-server-2013-backup-and-restoration-worksheets.md)所述所需的資訊。

  - 驗證方法是用來協助確保該資料和設定備份正確且可用來還原可以定期稽核或測試還原。

**還原服務**

備份和還原規劃應包含所有的必要資訊還原服務，以防一或多部伺服器發生，讓服務無法使用。 主要的資訊，以傳達給負責小組成員包含下列特性：

  - 小組或人員 （指定為個人或職位） 是負責判斷還原服務時所需和要用來還原服務及也小組或人員負責實作每個程序的程序還原案例。

  - 決定哪些還原程序最適合用於特定情況下的準則。

  - 服務及復原時間目標 (RTO) 每個還原案例的還原估計時間。

  - 若要使用，包括完成每項程序所需的工具的還原程序。

  - 若要還原資料和設定所需的資訊。 工作表會提供[Lync Server 2013 的備份及還原工作表](lync-server-2013-backup-and-restoration-worksheets.md)中。

</div>

<div>

## <a name="validating-backup-and-restoration-operations"></a>驗證備份與還原作業

完成後您實際執行環境中，並在指定的時間間隔 （做為您的備份和還原規劃所述） 的初步備份工作，您應該確認下列項目：

  - 視需要發生的備份。

  - 備份資料與設定均可存取。

  - 還原程序可備份和還原規劃，以及結果中所指定的時間內復原時間目標 (RTO) 符合所有業務需求。

  - 備份工作表已完成並驗證，以及它們會儲存在安全的位置。 這些工作表會提供[Lync Server 2013 的備份及還原工作表](lync-server-2013-backup-and-restoration-worksheets.md)中。

  - 還原程序已經測試並確認運作如預期運作，您的備份和還原規劃中所指定。

</div>

</div>

<div>

## <a name="maintaining-the-backup-and-restoration-plan"></a>維護備份和還原規劃

Lync Server 拓撲是動態的環境，變更與您的組織。 重新評估您的備份和還原規劃為您組織的變更，並檢閱定期以確定它會繼續以符合您的業務需求。

</div>

</div>

<span> </span>

</div>

</div>

</div>


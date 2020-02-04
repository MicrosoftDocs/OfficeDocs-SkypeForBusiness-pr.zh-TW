---
title: Lync Server 2013：後端伺服器高可用性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Back End Server high availability
ms:assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205248(v=OCS.15)
ms:contentKeyID: 48185358
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5708212aa2eb30cfcc3c3d40894ca2340475bd8b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740133"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="back-end-server-high-availability-in-lync-server-2013"></a>Lync Server 2013 的後端伺服器高可用性

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-08-12_

為了確保後端伺服器的高可用性，您可以使用同步 SQL 鏡像或 SQL 群集。 使用其中一種解決方案是選用的，但建議維持貴組織的業務連續性。 在 Lync Server 2013 中，後端伺服器高可用性不支援非同步 SQL 鏡像。 在本檔的其餘部分中，SQL 鏡像代表同步的 SQL 鏡像，除非明確指出。

您可以使用拓撲結構建立器輕鬆設定 SQL 鏡像。 對於 SQL 容錯移轉叢集，您必須使用 SQL Server 進行設定。

如果您在與災害復原的另一個前端池成對的 pool 中使用 SQL 鏡像或 SQL 群集，您應該在兩個池中使用相同的後端高可用性方案。 您不應該在使用 SQL 群集的情況中，將使用 SQL 鏡像與池進行配對。

當您部署 SQL 鏡像時，會對池中的所有 Lync Server 資料庫進行鏡像，包括中央管理儲存體（如果它位於此池中），以及回應群組應用程式資料庫及通話駐留應用程式資料庫（如果這些應用程式正在池中執行。

有了 SQL 鏡像，就不需要使用伺服器的共用儲存空間。 每個伺服器都會在本機儲存空間中保留自己的資料庫複本。

您可以選擇部署含或不含見證的 SQL 鏡像。 我們建議使用見證，因為它可讓後端伺服器的容錯移轉自動進行。 否則，系統管理員必須手動喚醒呼叫容錯移轉。 請注意，即使已部署見證，系統管理員也可以在必要時手動呼叫後端伺服器容錯移轉。

如果您使用見證，您可以針對多對後端伺服器使用單一見證。 Witnesses 和對後端伺服器之間沒有嚴格的1:1 對應。 針對多對後端伺服器使用單一見證伺服器的部署，不具彈性，因為每個後端伺服器對都有單獨的見證。

如需 SQL 群集支援的詳細資訊，請參閱[Lync Server 2013 中的資料庫軟體支援](lync-server-2013-database-software-support.md)。 如需有關部署 SQL 群集的詳細資料，請參閱[設定 Lync server 2013 的 SQL Server 群集](lync-server-2013-configure-sql-server-clustering.md)。

<div>

## <a name="recovery-time-for-automatic-back-end-server-failover-with-sql-mirroring"></a>使用 SQL 鏡像自動後端伺服器容錯移轉的恢復時間

如需使用 SQL 鏡像的自動後端容錯移轉，工程目標為復原時間目標（RTO）為5分鐘。 由於同步處理 SQL 的鏡像，我們不會在回退端伺服器失敗期間預計資料遺失，除非當前端伺服器和後端伺服器在伺服器間移動資料時，在一般情況下，就不會發生這種情況。 針對復原點目標（RPO）的工程目標是5分鐘。

</div>

<div>

## <a name="user-experience-during-back-end-server-failure-with-sql-mirroring"></a>在後端伺服器失敗的情況中使用 SQL 鏡像的使用者體驗

故障期間的使用者體驗取決於失敗的性質，以及拓撲。

如果您使用 SQL 鏡像且已設定見證伺服器，則主體會失敗，後端伺服器容錯移轉會自動及快速進行。 作用中的使用者不應該注意到他們的日常會話會有太大的中斷。

如果沒有設定見證，系統會在管理員手動呼叫容錯移轉時需要一些時間。 在這段時間內，作用中的使用者可能會受到影響。 它們會在大約30分鐘內繼續正常的會話。 如果主版仍未還原，或系統管理員沒有失敗轉移至備份，則使用者會切換到復原模式，這表示他們無法執行需要 Lync 伺服器上的永久變更的工作（例如新增連絡人）。

如果主體和鏡像後端伺服器失敗，或其中一個伺服器與見證伺服器發生故障，後端伺服器將變為無法使用（即使是仍在運作的主體）。 在這種情況下，作用中的使用者會在一段時間後切換為復原模式。

</div>

</div>

<span> </span>

</div>

</div>

</div>


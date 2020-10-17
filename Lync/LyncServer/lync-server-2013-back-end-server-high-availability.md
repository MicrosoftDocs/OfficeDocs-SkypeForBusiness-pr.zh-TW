---
title: Lync Server 2013：後端伺服器高可用性
description: Lync Server 2013：後端伺服器高可用性。
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
ms.openlocfilehash: 805cbf96e107329aa5c374cfa1e2d01234d360a3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543769"
---
# <a name="back-end-server-high-availability-in-lync-server-2013"></a>Lync Server 2013 中的後端伺服器高可用性

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-08-12_

為了確保後端伺服器的高可用性，您可以使用同步 SQL 鏡像或 SQL 叢集。 使用其中一種解決方案選用，但建議維護貴組織的業務持續性。 在 Lync Server 2013 中，不支援非同步 SQL 鏡像的後端伺服器高可用性。 在本文的其餘部分中，SQL 鏡像是指同步的 SQL 鏡像，除非特別明確指出。

您可以使用拓撲產生器輕鬆設定 SQL 鏡像。 針對 SQL 容錯移轉叢集，您必須使用 SQL Server 進行安裝。

如果您在與另一個前端集區成對的集區中使用 SQL 鏡像或 SQL 叢集，以進行嚴重損壞修復，您應該在兩個集區中使用相同的後端高可用性解決方案。 您不應該使用 sql 叢集與集區一起使用 SQL 鏡像，將集區配對。

當您部署 SQL 鏡像時，集區中的所有 Lync 伺服器資料庫都會進行鏡像，包括中央管理存放區（如果位於此集區中）以及回應群組應用程式資料庫及通話駐留應用程式資料庫（如果集區中正在執行這些應用程式）。

使用 SQL 鏡像，您不需要使用伺服器的共用儲存區。 每一部伺服器都會在本機儲存區中保留其資料庫複本。

您可以選擇使用或不使用見證來部署 SQL 鏡像。 我們建議使用見證，因為它可讓後端伺服器的容錯移轉成為自動。 否則，管理員必須手動呼叫容錯移轉。 請注意，即使部署見證，管理員也可以手動叫用後端伺服器容錯移轉（如有必要）。

如果您使用見證，您可以對多組的後端伺服器使用單一見證。 Witnesses 和後端伺服器對之間沒有嚴格的1:1 對應。 對多對後端伺服器使用單一見證的部署，並不像拓撲搭配每一組後端伺服器對具有個別的見證。

如需 SQL 群集支援的詳細資訊，請參閱 [Lync Server 2013 中的資料庫軟體支援](lync-server-2013-database-software-support.md)。 如需部署 SQL 叢集的詳細資訊，請參閱 [CONFIGURE Sql Server 叢集 For Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md)。

<div>

## <a name="recovery-time-for-automatic-back-end-server-failover-with-sql-mirroring"></a>使用 SQL 鏡像進行自動後端伺服器容錯移轉的復原時間

若要使用 SQL 鏡像進行自動後端容錯移轉，「恢復時間目標」的工程目標 (RTO) 為5分鐘。 因為同步 SQL 鏡像，所以在後端伺服器失敗的情況下，不會預見到資料遺失的情況，但在伺服器間移動資料時，一般情況下，當前端伺服器和後端伺服器都能同時停機的情況除外。 復原點目標的工程目標 (RPO) 為5分鐘。

</div>

<div>

## <a name="user-experience-during-back-end-server-failure-with-sql-mirroring"></a>使用 SQL 鏡像的後端伺服器失敗期間的使用者體驗

失敗期間的使用者經驗取決於失敗的性質和拓撲。

如果您使用 SQL 鏡像並已設定見證，但主體失敗，則後端伺服器容錯移轉會自動且快速地進行。 作用中使用者應該不會注意到其持續進行的會話中斷很大的狀態。

若未設定見證，系統管理員必須花一些時間來手動呼叫容錯移轉。 在這段時間內，作用中的使用者可能會受到影響。 他們會將其會話繼續正常等候30分鐘。 若主伺服器仍未還原，或系統管理員尚未容錯移轉至備份，使用者會切換至復原模式，也就是說，他們無法執行在 Lync Server (（例如新增連絡人) ）上需要持續變更的工作。

如果主體和鏡像的後端伺服器失敗，或其中一個伺服器和見證失敗，則即使是仍在運作) 主體，後端伺服器也會無法使用 (。 在此情況下，作用中的使用者會在一段時間後切換至復原模式。

</div>

</div>

<span> </span>

</div>

</div>

</div>


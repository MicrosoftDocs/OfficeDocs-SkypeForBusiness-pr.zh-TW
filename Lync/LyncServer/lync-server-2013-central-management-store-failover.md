---
title: Lync Server 2013 中央管理存放區容錯移轉
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Central Management store failover
ms:assetid: f464d715-68a4-462c-9584-00f41ab10db0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205376(v=OCS.15)
ms:contentKeyID: 48185809
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d19b045e23efa39c9f70f70ba7ac0236e77cc13
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135360"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="central-management-store-failover-in-lync-server-2013"></a><span data-ttu-id="e736c-102">Lync Server 2013 中的中央管理存放區容錯移轉</span><span class="sxs-lookup"><span data-stu-id="e736c-102">Central Management store failover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e736c-103">_**主題上次修改日期：** 2012年-10-18_</span><span class="sxs-lookup"><span data-stu-id="e736c-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="e736c-104">中央管理存放區包含伺服器和 Lync 2013 部署中的服務相關的組態資料。</span><span class="sxs-lookup"><span data-stu-id="e736c-104">The Central Management store contains configuration data about servers and services in your Lync 2013 deployment.</span></span> <span data-ttu-id="e736c-105">它提供穩定、 結構描述化為儲存區的定義、 設定、 維護、 管理、 說明，以及操作 Lync 2013 部署所需的資料。</span><span class="sxs-lookup"><span data-stu-id="e736c-105">It provides a robust, schematized storage of the data needed to define, set up, maintain, administer, describe, and operate a Lync 2013 deployment.</span></span> <span data-ttu-id="e736c-106">它也驗證資料，以確保設定一致性。</span><span class="sxs-lookup"><span data-stu-id="e736c-106">It also validates the data to ensure configuration consistency.</span></span>

<span data-ttu-id="e736c-107">每個 Lync 的部署包含一個中央管理存放區，這後端伺服器的一個前端集區所主控。</span><span class="sxs-lookup"><span data-stu-id="e736c-107">Each Lync deployment includes one Central Management store, which is hosted by the Back End Server of one Front End pool.</span></span>

<span data-ttu-id="e736c-108">當您建立集區配對，其中包含裝載的中央管理存放區的集區時，備份的中央管理存放區資料庫設定的備份集區，與服務會安裝在兩個集區的中央管理存放區中。</span><span class="sxs-lookup"><span data-stu-id="e736c-108">When you establish a pool pairing that includes the pool hosting the Central Management store, a backup Central Management store database is set up in the backup pool, and Central Management store services are installed in both pools.</span></span> <span data-ttu-id="e736c-109">在任何時間點，其中兩個中央管理存放區資料庫是作用中的主圖形，且另一個是待命。</span><span class="sxs-lookup"><span data-stu-id="e736c-109">At any point in time, one of the two Central Management store databases is the active master, and the other is a standby.</span></span> <span data-ttu-id="e736c-110">內容會複寫至待命從作用中主備份服務。</span><span class="sxs-lookup"><span data-stu-id="e736c-110">The content is replicated by the Backup Service from the active master to the standby.</span></span>

<span data-ttu-id="e736c-111">期間牽涉到主控的中央管理存放區的集區的集區容錯移轉，系統管理員必須容錯移轉前失敗的中央管理存放區上的前端集區。</span><span class="sxs-lookup"><span data-stu-id="e736c-111">During a pool failover that involves the pools hosting the Central Management store, the administrator must fail over the Central Management store before failing over the Front End pool.</span></span>

<span data-ttu-id="e736c-112">嚴重損壞修復後，它不需要容錯回復的中央管理存放區。</span><span class="sxs-lookup"><span data-stu-id="e736c-112">After the disaster is repaired, it is not necessary to fail back the Central Management store.</span></span> <span data-ttu-id="e736c-113">修復後，在原始的備份集區的中央管理存放區可以保持為作用中的主圖形。</span><span class="sxs-lookup"><span data-stu-id="e736c-113">After repair, the Central Management store in the original backup pool can remain as the active master.</span></span>

<span data-ttu-id="e736c-114">中央管理存放區容錯移轉的程式設計目標是 5 分鐘，復原時間目標 (RTO) 和 5 分鐘，復原點目標 (RPO)。</span><span class="sxs-lookup"><span data-stu-id="e736c-114">The engineering targets for Central Management store failover are 5 minutes for recovery time objective (RTO) and 5 minutes for recovery point objective (RPO).</span></span>

</div>

<span> </span>

</div>

</div>

</div>


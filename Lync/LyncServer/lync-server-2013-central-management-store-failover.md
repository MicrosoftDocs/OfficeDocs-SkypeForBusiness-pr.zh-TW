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
ms.openlocfilehash: 675f5b8e2880303a99897da18f44047c73961e4a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508040"
---
# <a name="central-management-store-failover-in-lync-server-2013"></a><span data-ttu-id="ff537-102">Lync Server 2013 中的中央管理存放區容錯移轉</span><span class="sxs-lookup"><span data-stu-id="ff537-102">Central Management store failover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff537-103">_**主題上次修改日期：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="ff537-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="ff537-104">中央管理存放區包含 Lync 2013 部署中伺服器和服務的設定資料。</span><span class="sxs-lookup"><span data-stu-id="ff537-104">The Central Management store contains configuration data about servers and services in your Lync 2013 deployment.</span></span> <span data-ttu-id="ff537-105">它可為定義、設定、維護、管理、描述及操作 Lync 2013 部署所需的資料提供強健的 schematized 儲存。</span><span class="sxs-lookup"><span data-stu-id="ff537-105">It provides a robust, schematized storage of the data needed to define, set up, maintain, administer, describe, and operate a Lync 2013 deployment.</span></span> <span data-ttu-id="ff537-106">它也驗證資料，以確保設定一致性。</span><span class="sxs-lookup"><span data-stu-id="ff537-106">It also validates the data to ensure configuration consistency.</span></span>

<span data-ttu-id="ff537-107">每個 Lync 部署都包含一個中央管理存放區，由一個前端集區的後端伺服器主控。</span><span class="sxs-lookup"><span data-stu-id="ff537-107">Each Lync deployment includes one Central Management store, which is hosted by the Back End Server of one Front End pool.</span></span>

<span data-ttu-id="ff537-108">當您建立的集區配對包含主控中央管理存放區的集區時，會在備份組區中設定備份中央管理存放區資料庫，並在兩個集區中安裝中央管理存放區服務。</span><span class="sxs-lookup"><span data-stu-id="ff537-108">When you establish a pool pairing that includes the pool hosting the Central Management store, a backup Central Management store database is set up in the backup pool, and Central Management store services are installed in both pools.</span></span> <span data-ttu-id="ff537-109">在任何時間點，其中一個中央管理存放區資料庫是作用中的主資料庫，另一個則是待機狀態。</span><span class="sxs-lookup"><span data-stu-id="ff537-109">At any point in time, one of the two Central Management store databases is the active master, and the other is a standby.</span></span> <span data-ttu-id="ff537-110">備份服務會將內容從使用中主圖形複製到待機狀態。</span><span class="sxs-lookup"><span data-stu-id="ff537-110">The content is replicated by the Backup Service from the active master to the standby.</span></span>

<span data-ttu-id="ff537-111">在包含主控中央管理存放區之集區的集區容錯移轉期間，管理員必須先容錯移轉中央管理存放區，再失敗轉移前端集區。</span><span class="sxs-lookup"><span data-stu-id="ff537-111">During a pool failover that involves the pools hosting the Central Management store, the administrator must fail over the Central Management store before failing over the Front End pool.</span></span>

<span data-ttu-id="ff537-112">修復災難後，不需要對中央管理存放區進行容錯回復。</span><span class="sxs-lookup"><span data-stu-id="ff537-112">After the disaster is repaired, it is not necessary to fail back the Central Management store.</span></span> <span data-ttu-id="ff537-113">修復之後，原始備份組區中的中央管理存放區可以保留為作用中主圖形。</span><span class="sxs-lookup"><span data-stu-id="ff537-113">After repair, the Central Management store in the original backup pool can remain as the active master.</span></span>

<span data-ttu-id="ff537-114">集中式管理存放區容錯移轉的工程目標是5分鐘的復原時間目標 (RTO) 和5分鐘用於復原點目標 (RPO) 。</span><span class="sxs-lookup"><span data-stu-id="ff537-114">The engineering targets for Central Management store failover are 5 minutes for recovery time objective (RTO) and 5 minutes for recovery point objective (RPO).</span></span>

</div>

<span> </span>

</div>

</div>

</div>


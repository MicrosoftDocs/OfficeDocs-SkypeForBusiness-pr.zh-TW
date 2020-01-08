---
title: 部署 Lync Server 2013 用戶端
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploy Lync Server 2013 clients
ms:assetid: 508e5dfa-588b-4289-81ce-2043c2d79e04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204883(v=OCS.15)
ms:contentKeyID: 48184100
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 659ec7be51358e73824c322461a3e27a163dc1bf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982695"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-clients"></a><span data-ttu-id="351f1-102">部署 Lync Server 2013 用戶端</span><span class="sxs-lookup"><span data-stu-id="351f1-102">Deploy Lync Server 2013 clients</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="351f1-103">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="351f1-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="351f1-104">將使用者遷移至 Lync Server 2013 之後，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="351f1-104">After you migrate users to Lync Server 2013, do the following:</span></span>

1.  <span data-ttu-id="351f1-105">在新的 Lync Server 2013 server 上使用用戶端版本篩選器，只允許已安裝最新更新的用戶端登入。</span><span class="sxs-lookup"><span data-stu-id="351f1-105">Use the Client Version Filter on the new Lync Server 2013 server to only allow clients with the most current updates installed to sign in.</span></span>

2.  <span data-ttu-id="351f1-106">如有需要，請設定用戶端引導所需的群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="351f1-106">If necessary, configure the Group Policy settings that are required for client bootstrapping.</span></span> <span data-ttu-id="351f1-107">如需詳細資訊，請參閱在部署檔中的[Lync Server 2013 中設定用戶端引導原則](lync-server-2013-configuring-client-bootstrapping-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="351f1-107">For details, see [Configuring client bootstrapping policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) in the Deployment documentation.</span></span> <span data-ttu-id="351f1-108">只有在您想要變更現有的用戶端引導原則或您想要設定新的用戶端引導原則時，才需要設定這些設定。</span><span class="sxs-lookup"><span data-stu-id="351f1-108">Configuration of these settings is only necessary if you want to change existing client bootstrapping policies or if you want to set new client bootstrapping policies.</span></span> <span data-ttu-id="351f1-109">如果您不打算設定用戶端引導原則，或您想要將舊版用戶端引導原則保持生效，則無需執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="351f1-109">If you do not plan to configure client bootstrapping policies, or you want legacy client bootstrapping policies to remain in effect, no action is necessary.</span></span>

3.  <span data-ttu-id="351f1-110">使用 Lync Server 2013 [控制台]、[Lync Server 2013 管理命令介面] 或 [兩者]，為特定的使用者或使用者群組設定其他使用者和用戶端原則。</span><span class="sxs-lookup"><span data-stu-id="351f1-110">Configure other user and client policies for specific users or groups of users by using Lync Server 2013 Control Panel, Lync Server 2013 Management Shell, or both.</span></span> <span data-ttu-id="351f1-111">如需詳細資訊，請參閱規劃檔中的[Lync 2013 新增及變更設定](lync-server-2013-new-and-changed-settings-for-lync-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="351f1-111">For details, see [New and changed settings for Lync 2013](lync-server-2013-new-and-changed-settings-for-lync-2013.md) in the Planning documentation.</span></span>

4.  <span data-ttu-id="351f1-112">部署最新版本的 Lync Server 2013 用戶端及最新的累加更新。</span><span class="sxs-lookup"><span data-stu-id="351f1-112">Deploy the latest version of Lync Server 2013 clients along with the latest cumulative updates.</span></span> <span data-ttu-id="351f1-113">如需詳細資訊，請參閱部署檔中的[Lync Server 2013 中的 [部署用戶端和裝置](lync-server-2013-deploying-clients-and-devices.md)]。</span><span class="sxs-lookup"><span data-stu-id="351f1-113">For details, see [Deploying clients and devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) in the Deployment documentation.</span></span>

5.  <span data-ttu-id="351f1-114">可選如果您的組織需要 Lync Server 2013 增強的目前狀態隱私權模式，在完成遷移之後，定義用戶端版本原則規則，以避免舊版用戶端版本登入。</span><span class="sxs-lookup"><span data-stu-id="351f1-114">(Optional) If your organization requires Lync Server 2013 enhanced presence privacy mode, after migration is complete, define a Client Version Policy Rule to prevent earlier client versions from signing in.</span></span> <span data-ttu-id="351f1-115">然後，啟用 [增強的目前狀態隱私權模式]。</span><span class="sxs-lookup"><span data-stu-id="351f1-115">Then, enable enhanced presence privacy mode.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="351f1-116">請勿啟用 Lync 2013 增強的目前狀態隱私權模式，直到特定伺服器池中的每個使用者都安裝了最新的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="351f1-116">Do not enable Lync 2013 enhanced presence privacy mode until every user on a given server pool has the most current client versions installed.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>


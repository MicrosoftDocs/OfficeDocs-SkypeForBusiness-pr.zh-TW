---
title: 'Lync Server 2013: Configuring Call Park'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Call Park
ms:assetid: e4c5da53-7f6c-4535-bc9b-9da2026caec8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399014(v=OCS.15)
ms:contentKeyID: 48185732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae622224f6fa399de4aac97b0ed06b679f8147f7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146986"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-call-park-in-lync-server-2013"></a><span data-ttu-id="69a75-102">在 Lync Server 2013 中設定通話駐留</span><span class="sxs-lookup"><span data-stu-id="69a75-102">Configuring Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69a75-103">_**主題上次修改日期：** 2012年-10-30_</span><span class="sxs-lookup"><span data-stu-id="69a75-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="69a75-104">通話駐留可讓 Enterprise Voice 使用者從一個電話將呼叫放入保留及更新版本來撥打內部號碼 （亦即通話駐留*軌道*） 透過任何電話擷取通話。</span><span class="sxs-lookup"><span data-stu-id="69a75-104">Call Park enables an Enterprise Voice user to put a call on hold from one telephone and then retrieve the call later by dialing an internal number (known as a Call Park *orbit*) from any telephone.</span></span>

<span data-ttu-id="69a75-105">通話駐留使用的元件會自動安裝並啟用在前端伺服器或 Standard Edition 伺服器，當您部署企業語音。</span><span class="sxs-lookup"><span data-stu-id="69a75-105">The components that Call Park uses are automatically installed and enabled on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="69a75-106">不過，您必須先設定通話駐留，再可供使用者。</span><span class="sxs-lookup"><span data-stu-id="69a75-106">However, you must configure Call Park before it is available to users.</span></span>

<span data-ttu-id="69a75-107">本節會引導您完成的通話駐留組態。</span><span class="sxs-lookup"><span data-stu-id="69a75-107">This section guides you through the configuration of Call Park.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="69a75-108">本章節內容</span><span class="sxs-lookup"><span data-stu-id="69a75-108">In This Section</span></span>

  - [<span data-ttu-id="69a75-109">通話駐留組態先決條件和 Lync Server 2013 中的使用者權限</span><span class="sxs-lookup"><span data-stu-id="69a75-109">Call Park configuration prerequisites and user rights in Lync Server 2013</span></span>](lync-server-2013-call-park-configuration-prerequisites-and-user-rights.md)

  - [<span data-ttu-id="69a75-110">Lync Server 2013 中的通話駐留的部署程序</span><span class="sxs-lookup"><span data-stu-id="69a75-110">Deployment process for Call Park in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-call-park.md)

  - [<span data-ttu-id="69a75-111">Lync Server 2013 中設定通話駐留軌道表</span><span class="sxs-lookup"><span data-stu-id="69a75-111">Configure the Call Park orbit table in Lync Server 2013</span></span>](lync-server-2013-configure-the-call-park-orbit-table.md)

  - [<span data-ttu-id="69a75-112">在 Lync Server 2013 中設定通話駐留設定</span><span class="sxs-lookup"><span data-stu-id="69a75-112">Configure Call Park settings in Lync Server 2013</span></span>](lync-server-2013-configure-call-park-settings.md)

  - [<span data-ttu-id="69a75-113">自訂通話駐留等候音樂 Lync Server 2013 中</span><span class="sxs-lookup"><span data-stu-id="69a75-113">Customize Call Park music on hold in Lync Server 2013</span></span>](lync-server-2013-customize-call-park-music-on-hold.md)

  - [<span data-ttu-id="69a75-114">啟用 Lync Server 2013 中的使用者的通話駐留</span><span class="sxs-lookup"><span data-stu-id="69a75-114">Enable Call Park for users in Lync Server 2013</span></span>](lync-server-2013-enable-call-park-for-users.md)

  - [<span data-ttu-id="69a75-115">確認 Lync Server 2013 中的通話駐留的正規化規則</span><span class="sxs-lookup"><span data-stu-id="69a75-115">Verify normalization rules for Call Park in Lync Server 2013</span></span>](lync-server-2013-verify-normalization-rules-for-call-park.md)

  - [<span data-ttu-id="69a75-116">（選用）確認 Lync Server 2013 中的通話駐留部署</span><span class="sxs-lookup"><span data-stu-id="69a75-116">(Optional) Verify Call Park deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-call-park-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


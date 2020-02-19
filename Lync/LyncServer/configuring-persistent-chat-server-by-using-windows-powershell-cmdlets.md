---
title: 使用 Windows PowerShell cmdlet 設定常設聊天室伺服器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configuring Persistent Chat Server by using Windows PowerShell cmdlets
ms:assetid: 4c1d1ad7-b6bd-476f-9c5b-f0c1756d5aa8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204877(v=OCS.15)
ms:contentKeyID: 48184089
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc898bbc9338bbb87ee7ee2626f108b1461d4971
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135960"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a053b-102">使用 Windows PowerShell cmdlet 設定常設聊天室伺服器</span><span class="sxs-lookup"><span data-stu-id="a053b-102">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a053b-103">_**主題上次修改日期：** 2012年-10-06_</span><span class="sxs-lookup"><span data-stu-id="a053b-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="a053b-104">使用下列 Windows PowerShell cmdlet 設定 Lync Server 2013，Persistent Chat Server 內的管理。</span><span class="sxs-lookup"><span data-stu-id="a053b-104">Use the following Windows PowerShell cmdlets to configure management within Lync Server 2013, Persistent Chat Server.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a053b-105">本章節內容</span><span class="sxs-lookup"><span data-stu-id="a053b-105">In This Section</span></span>

  - [<span data-ttu-id="a053b-106">管理類別</span><span class="sxs-lookup"><span data-stu-id="a053b-106">Manage categories</span></span>](manage-categories.md)

  - [<span data-ttu-id="a053b-107">管理聊天室</span><span class="sxs-lookup"><span data-stu-id="a053b-107">Manage rooms</span></span>](manage-rooms.md)

  - [<span data-ttu-id="a053b-108">管理增益集</span><span class="sxs-lookup"><span data-stu-id="a053b-108">Manage add-ins</span></span>](manage-add-ins.md)

  - [<span data-ttu-id="a053b-109">移除訊息</span><span class="sxs-lookup"><span data-stu-id="a053b-109">Remove a message</span></span>](remove-a-message.md)

  - [<span data-ttu-id="a053b-110">利用綜合交易測試常設聊天室伺服器</span><span class="sxs-lookup"><span data-stu-id="a053b-110">Test Persistent Chat Server with a synthetic transaction</span></span>](test-persistent-chat-server-with-a-synthetic-transaction.md)

  - [<span data-ttu-id="a053b-111">針對常設聊天室伺服器執行回溯相容性</span><span class="sxs-lookup"><span data-stu-id="a053b-111">Run backward compatibility for Persistent Chat Server</span></span>](run-backward-compatibility-for-persistent-chat-server.md)

  - [<span data-ttu-id="a053b-112">執行、 授與、 取得、 移除或 Lync Server 2013 中設定常設聊天室原則</span><span class="sxs-lookup"><span data-stu-id="a053b-112">Run, grant, get, remove, or set Persistent Chat Policy in Lync Server 2013</span></span>](lync-server-2013-run-grant-get-remove-or-set-persistent-chat-policy.md)

  - [<span data-ttu-id="a053b-113">在 Lync Server 2013 中設定常設聊天室伺服器</span><span class="sxs-lookup"><span data-stu-id="a053b-113">Configure Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-configure-persistent-chat-server.md)

  - <span data-ttu-id="a053b-114">[在 [Lync Server 2013 取得 Persistent Chat Server 集區可用性](lync-server-2013-get-persistent-chat-server-pool-availability.md)</span><span class="sxs-lookup"><span data-stu-id="a053b-114">[Get Persistent Chat Server pool availability in Lync Server 2013](lync-server-2013-get-persistent-chat-server-pool-availability.md)</span></span>

  - <span data-ttu-id="a053b-115">[在 [Lync Server 2013 常設聊天室規範](lync-server-2013-persistent-chat-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="a053b-115">[Persistent Chat compliance in Lync Server 2013](lync-server-2013-persistent-chat-compliance.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


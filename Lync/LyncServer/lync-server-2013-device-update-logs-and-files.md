---
title: Lync Server 2013：裝置更新記錄與檔案
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device Update logs and files
ms:assetid: f7f822b8-0a62-4ff2-a4cb-1ab1ed7503eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994090(v=OCS.15)
ms:contentKeyID: 51804004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23dd149a16a89e3ffbb11f5553cda3ab6e4530b8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501470"
---
# <a name="device-update-logs-and-files-in-lync-server-2013"></a><span data-ttu-id="3e795-102">Lync Server 2013 中的裝置更新記錄和檔案</span><span class="sxs-lookup"><span data-stu-id="3e795-102">Device Update logs and files in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e795-103">_**主題上次修改日期：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="3e795-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="3e795-104">裝置更新記錄檔包含重要資訊，可供您用來管理裝置更新 Web 服務並加以疑難排解。</span><span class="sxs-lookup"><span data-stu-id="3e795-104">Device update logs contain important information that you can use to manage and troubleshoot the Device Update Web service.</span></span> <span data-ttu-id="3e795-105">您可以變更所記錄的內容，並移除不需要或不再需要的裝置記錄檔和更新。</span><span class="sxs-lookup"><span data-stu-id="3e795-105">You can change what is logged and remove device logs and updates that you don’t want or no longer need.</span></span> <span data-ttu-id="3e795-106">本節說明如何使用 Lync Server 控制台或 Lync Server 管理命令介面來修改記錄設定、清除裝置更新記錄檔，或從伺服器移除記錄檔。</span><span class="sxs-lookup"><span data-stu-id="3e795-106">This section describes how you can use Lync Server Control Panel or Lync Server Management Shell to modify logging settings, clear the device update log, or remove log files from the server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3e795-107">如需裝置更新記錄檔的詳細資訊，請參閱 Lync Server 2010 TechNet 程式庫中的 <A href="https://technet.microsoft.com/library/gg398250(v=ocs.14).aspx">記錄檔類型和位置</A> 。</span><span class="sxs-lookup"><span data-stu-id="3e795-107">For details about device update log files, see <A href="https://technet.microsoft.com/library/gg398250(v=ocs.14).aspx">Log File Types and Locations</A> in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="3e795-108"> (請注意，裝置更新 Web 服務（如所有 Lync Phone Edition 元件）的運作方式與 lync server 2010 2013 相同。 ) </span><span class="sxs-lookup"><span data-stu-id="3e795-108">(Note that the Device Update Web service, like all Lync Phone Edition components, works the same way with Lync Server 2013 as it does with Lync Server 2010.)</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3e795-109">本章節內容</span><span class="sxs-lookup"><span data-stu-id="3e795-109">In This Section</span></span>

  - [<span data-ttu-id="3e795-110">在 Lync Server 2013 中修改裝置更新記錄檔的設定</span><span class="sxs-lookup"><span data-stu-id="3e795-110">Modify settings for Device Update log files in Lync Server 2013</span></span>](lync-server-2013-modify-settings-for-device-update-log-files.md)

  - [<span data-ttu-id="3e795-111">在 Lync Server 2013 中刪除裝置更新記錄檔</span><span class="sxs-lookup"><span data-stu-id="3e795-111">Delete Device Update log files in Lync Server 2013</span></span>](lync-server-2013-delete-device-update-log-files.md)

  - [<span data-ttu-id="3e795-112">移除與移除裝置更新檔案中未關聯之裝置的裝置更新檔案（與 Lync Server 2013 中未關聯的裝置）</span><span class="sxs-lookup"><span data-stu-id="3e795-112">Remove Device Update files not associated with a device in Remove Device Update files not associated with a device in Lync Server 2013</span></span>](lync-server-2013-remove-device-update-files-not-associated-with-a-device.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


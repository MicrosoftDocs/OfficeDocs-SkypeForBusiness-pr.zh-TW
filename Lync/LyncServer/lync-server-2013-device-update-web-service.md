---
title: Lync Server 2013：裝置更新 Web 服務
description: Lync Server 2013：裝置更新 Web 服務。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device Update Web service
ms:assetid: 036f473d-a131-431f-8051-76ccadc5cfba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994015(v=OCS.15)
ms:contentKeyID: 51803921
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45511d34ab99f295481472f2a3c14bf21da32ff6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565949"
---
# <a name="device-update-web-service-in-lync-server-2013"></a><span data-ttu-id="d6165-103">Lync Server 2013 中的裝置更新 Web 服務</span><span class="sxs-lookup"><span data-stu-id="d6165-103">Device Update Web service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6165-104">_**主題上次修改日期：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="d6165-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="d6165-105">Lync Server 包含裝置更新 Web 服務，此服務會自動安裝為 Web 服務角色的一部分。</span><span class="sxs-lookup"><span data-stu-id="d6165-105">Lync Server includes the Device Update Web service, which is automatically installed as part of the Web Services role.</span></span> <span data-ttu-id="d6165-106">此項服務可讓您從 Microsoft 下載更新，加以測試，然後將更新部署至您組織中的 IP 電話。</span><span class="sxs-lookup"><span data-stu-id="d6165-106">This service lets you download updates from Microsoft, test them, and then deploy the updates to IP phones in your organization.</span></span> <span data-ttu-id="d6165-107">您也可以使用裝置更新 Web 服務，將裝置復原為舊版的軟體版本。</span><span class="sxs-lookup"><span data-stu-id="d6165-107">You can also use Device Update Web service to roll back devices to previous software versions.</span></span>

<span data-ttu-id="d6165-108">本節提供有關如何使用裝置更新記錄檔管理裝置更新 Web 服務及部署更新的詳細資訊，rules (Lync Phone Edition 使用 *規則* ，將固件版本更新與硬體裝置關聯) 和設定設定。</span><span class="sxs-lookup"><span data-stu-id="d6165-108">This section provides details about how to manage the Device Update Web service and deployed updates by using device update logs, rules (Lync Phone Edition uses *rules* to associate firmware version updates with hardware devices), and configuration settings.</span></span>

<span data-ttu-id="d6165-109">如需裝置更新 Web 服務處理常式和功能的詳細資訊，請參閱更新 Lync Server 2010 TechNet 程式庫中的 [裝置](https://technet.microsoft.com/library/gg412864\(v=ocs.14\).aspx) 。</span><span class="sxs-lookup"><span data-stu-id="d6165-109">For details about the Device Update Web service process and features, see [Updating Devices](https://technet.microsoft.com/library/gg412864\(v=ocs.14\).aspx) in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="d6165-110"> (請注意，裝置更新 Web 服務（如所有 Lync Phone Edition 元件）的運作方式與 lync server 2010 2013 相同。 ) </span><span class="sxs-lookup"><span data-stu-id="d6165-110">(Note that the Device Update Web service, like all Lync Phone Edition components, works the same way with Lync Server 2013 as it does with Lync Server 2010.)</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d6165-111">本章節內容</span><span class="sxs-lookup"><span data-stu-id="d6165-111">In This Section</span></span>

  - [<span data-ttu-id="d6165-112">Lync Server 2013 中的裝置更新記錄和檔案</span><span class="sxs-lookup"><span data-stu-id="d6165-112">Device Update logs and files in Lync Server 2013</span></span>](lync-server-2013-device-update-logs-and-files.md)

  - [<span data-ttu-id="d6165-113">Lync Server 2013 中的裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="d6165-113">Device Update rules in Lync Server 2013</span></span>](lync-server-2013-device-update-rules.md)

  - [<span data-ttu-id="d6165-114">Lync Server 2013 中的裝置更新設定設定</span><span class="sxs-lookup"><span data-stu-id="d6165-114">Device Update configuration settings in Lync Server 2013</span></span>](lync-server-2013-device-update-configuration-settings.md)

  - [<span data-ttu-id="d6165-115">在 Lync Server 2013 中查看裝置的軟體更新</span><span class="sxs-lookup"><span data-stu-id="d6165-115">View software updates for devices in Lync Server 2013</span></span>](lync-server-2013-view-software-updates-for-devices-in-your-organization.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d6165-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d6165-116">See Also</span></span>


<span data-ttu-id="d6165-117">[管理及疑難排解裝置的工具與服務](https://technet.microsoft.com/library/gg425800\(v=ocs.14\).aspx)</span><span class="sxs-lookup"><span data-stu-id="d6165-117">[Tools and Services for Managing and Troubleshooting Devices](https://technet.microsoft.com/library/gg425800\(v=ocs.14\).aspx)</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


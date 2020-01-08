---
title: Lync Server 2013：裝置更新 Web 服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Device Update Web service
ms:assetid: 036f473d-a131-431f-8051-76ccadc5cfba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994015(v=OCS.15)
ms:contentKeyID: 51803921
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d2b258b7a088f0deeee029be482f1ed63bc00ef
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982449"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-update-web-service-in-lync-server-2013"></a><span data-ttu-id="bb772-102">Lync Server 2013 中的裝置更新 Web 服務</span><span class="sxs-lookup"><span data-stu-id="bb772-102">Device Update Web service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb772-103">_**主題上次修改日期：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="bb772-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="bb772-104">Lync Server 包含裝置更新 Web 服務，此服務會自動安裝為 Web 服務角色的一部分。</span><span class="sxs-lookup"><span data-stu-id="bb772-104">Lync Server includes the Device Update Web service, which is automatically installed as part of the Web Services role.</span></span> <span data-ttu-id="bb772-105">此服務可讓您從 Microsoft 下載更新，進行測試，然後將更新部署到貴組織中的 IP 電話。</span><span class="sxs-lookup"><span data-stu-id="bb772-105">This service lets you download updates from Microsoft, test them, and then deploy the updates to IP phones in your organization.</span></span> <span data-ttu-id="bb772-106">您也可以使用裝置更新 Web 服務，將裝置回滾到舊版軟體版本。</span><span class="sxs-lookup"><span data-stu-id="bb772-106">You can also use Device Update Web service to roll back devices to previous software versions.</span></span>

<span data-ttu-id="bb772-107">本節詳細說明如何使用裝置更新記錄來管理裝置更新 Web 服務和部署更新，規則（Lync Phone Edition 會使用*規則*將固件版本更新與硬體裝置進行關聯），以及設定設定。</span><span class="sxs-lookup"><span data-stu-id="bb772-107">This section provides details about how to manage the Device Update Web service and deployed updates by using device update logs, rules (Lync Phone Edition uses *rules* to associate firmware version updates with hardware devices), and configuration settings.</span></span>

<span data-ttu-id="bb772-108">如需裝置更新 Web 服務程式和功能的詳細資訊，請參閱更新 Lync Server 2010 TechNet 文件庫中的[裝置](http://technet.microsoft.com/en-us/library/gg412864\(v=ocs.14\).aspx)。</span><span class="sxs-lookup"><span data-stu-id="bb772-108">For details about the Device Update Web service process and features, see [Updating Devices](http://technet.microsoft.com/en-us/library/gg412864\(v=ocs.14\).aspx) in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="bb772-109">（請注意，裝置更新 Web 服務（例如所有 Lync 手機版本元件）的運作方式2013與 Lync Server 2010 相同。）</span><span class="sxs-lookup"><span data-stu-id="bb772-109">(Note that the Device Update Web service, like all Lync Phone Edition components, works the same way with Lync Server 2013 as it does with Lync Server 2010.)</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bb772-110">本節內容</span><span class="sxs-lookup"><span data-stu-id="bb772-110">In This Section</span></span>

  - [<span data-ttu-id="bb772-111">Lync Server 2013 中的裝置更新記錄和檔案</span><span class="sxs-lookup"><span data-stu-id="bb772-111">Device Update logs and files in Lync Server 2013</span></span>](lync-server-2013-device-update-logs-and-files.md)

  - [<span data-ttu-id="bb772-112">Lync Server 2013 中的裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="bb772-112">Device Update rules in Lync Server 2013</span></span>](lync-server-2013-device-update-rules.md)

  - [<span data-ttu-id="bb772-113">Lync Server 2013 中的裝置更新設定設定</span><span class="sxs-lookup"><span data-stu-id="bb772-113">Device Update configuration settings in Lync Server 2013</span></span>](lync-server-2013-device-update-configuration-settings.md)

  - [<span data-ttu-id="bb772-114">在 Lync Server 2013 中查看裝置的軟體更新</span><span class="sxs-lookup"><span data-stu-id="bb772-114">View software updates for devices in Lync Server 2013</span></span>](lync-server-2013-view-software-updates-for-devices-in-your-organization.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bb772-115">請參閱</span><span class="sxs-lookup"><span data-stu-id="bb772-115">See Also</span></span>


<span data-ttu-id="bb772-116">[管理和疑難排解裝置的工具與服務](http://technet.microsoft.com/en-us/library/gg425800\(v=ocs.14\).aspx)</span><span class="sxs-lookup"><span data-stu-id="bb772-116">[Tools and Services for Managing and Troubleshooting Devices](http://technet.microsoft.com/en-us/library/gg425800\(v=ocs.14\).aspx)</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013：配置支援的用戶端版本
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring supported client versions
ms:assetid: aebf7b48-9aa2-4a06-adc5-0c9d11b6358d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412832(v=OCS.15)
ms:contentKeyID: 48185137
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a262cab2145013d83cdae573d98b5db17e0e890
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734773"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-supported-client-versions-in-lync-server-2013"></a><span data-ttu-id="91c6a-102">在 Lync Server 2013 中設定支援的用戶端版本</span><span class="sxs-lookup"><span data-stu-id="91c6a-102">Configuring supported client versions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91c6a-103">_**主題上次修改日期：** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="91c6a-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="91c6a-104">在 Lync Server 2013 中，您可以設定用戶端版本原則，以指定您的環境支援的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="91c6a-104">In Lync Server 2013, you can set up client version policies to specify the versions of clients that are supported in your environment.</span></span> <span data-ttu-id="91c6a-105">此外，您也可以使用全域用戶端版本設定，為尚未定義版本原則的用戶端指定預設動作，因此，不是明確支援或受限制。</span><span class="sxs-lookup"><span data-stu-id="91c6a-105">Additionally, you can use the global client version configuration to specify a default action for clients that do not already have a version policy defined and, therefore, are not explicitly supported or restricted.</span></span>

<span data-ttu-id="91c6a-106">您也可以使用用戶端版本原則來管理用戶端更新。</span><span class="sxs-lookup"><span data-stu-id="91c6a-106">You can also use client version policies to manage client updates.</span></span> <span data-ttu-id="91c6a-107">當您設定用戶端版本原則並使用選項 [**允許**] 和 [升級及**封鎖及升級**] 時，用戶端將會從 Windows Server Update services 接收更新的軟體（如果您使用的是此服務）或 [Microsoft Update]。</span><span class="sxs-lookup"><span data-stu-id="91c6a-107">When you set a client version policy and use the options **Allow and upgrade** and **Block and upgrade**, clients will receive updated software from the Windows Server Update Service (if you are using this service) or from Microsoft Update.</span></span>

<div>

## <a name="client-version-policy-settings"></a><span data-ttu-id="91c6a-108">用戶端版本原則設定</span><span class="sxs-lookup"><span data-stu-id="91c6a-108">Client Version Policy Settings</span></span>

<span data-ttu-id="91c6a-109">預設用戶端版本原則要求所有用戶端都執行 Lync。</span><span class="sxs-lookup"><span data-stu-id="91c6a-109">The default client version policy requires that all clients run Lync.</span></span> <span data-ttu-id="91c6a-110">如果您環境中的用戶端執行舊版的 Communicator，您可能需要重新設定用戶端版本規則，以免在連線至 Lync Server 2013 時，意外地封鎖或更新用戶端裝置。</span><span class="sxs-lookup"><span data-stu-id="91c6a-110">If clients in your environment are running earlier versions of Communicator, you may need to reconfigure the Client Version rules to prevent clients and devices from being unexpectedly blocked or updated when connecting to Lync Server 2013.</span></span> <span data-ttu-id="91c6a-111">您可以修改預設規則，或者您可以在用戶端版本原則清單中新增較高的規則，以覆寫預設規則。</span><span class="sxs-lookup"><span data-stu-id="91c6a-111">You can modify the default rule, or you can add a rule higher in the Client Version Policy list to override the default rule.</span></span> <span data-ttu-id="91c6a-112">此外，隨著累加更新（CUs）的發行，您應該將用戶端版本原則設定為需要最新的更新。</span><span class="sxs-lookup"><span data-stu-id="91c6a-112">Additionally, as Cumulative Updates (CUs) are released, you should configure the Client Version Policy to require the latest updates.</span></span> <span data-ttu-id="91c6a-113">如需詳細資訊，請參閱在作業檔中[指定可用於登入 Lync Server 2013 的用戶端應用程式](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="91c6a-113">For details, see [Specifying the client applications that can be used to log on to Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md) in the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


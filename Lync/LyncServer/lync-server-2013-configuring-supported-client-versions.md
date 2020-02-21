---
title: Lync Server 2013： 設定支援的用戶端版本
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
ms.openlocfilehash: 34d74de1ae5e25c372e51783d8321ebc8699eaef
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202889"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-supported-client-versions-in-lync-server-2013"></a><span data-ttu-id="e66e0-102">在 Lync Server 2013 中設定支援的用戶端版本</span><span class="sxs-lookup"><span data-stu-id="e66e0-102">Configuring supported client versions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e66e0-103">_**主題上次修改日期：** 2012年-12-14_</span><span class="sxs-lookup"><span data-stu-id="e66e0-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="e66e0-104">在 Lync Server 2013 中，您可以設定來指定您的環境中支援的用戶端版本的用戶端版本原則。</span><span class="sxs-lookup"><span data-stu-id="e66e0-104">In Lync Server 2013, you can set up client version policies to specify the versions of clients that are supported in your environment.</span></span> <span data-ttu-id="e66e0-105">此外，您可以使用全域的用戶端版本設定來指定預設巨集指令還沒有版本的用戶端原則定義，因此，都沒有明確支援或限制。</span><span class="sxs-lookup"><span data-stu-id="e66e0-105">Additionally, you can use the global client version configuration to specify a default action for clients that do not already have a version policy defined and, therefore, are not explicitly supported or restricted.</span></span>

<span data-ttu-id="e66e0-106">您也可以使用用戶端版本原則來管理用戶端更新。</span><span class="sxs-lookup"><span data-stu-id="e66e0-106">You can also use client version policies to manage client updates.</span></span> <span data-ttu-id="e66e0-107">當您設定用戶端版本原則，並使用 **[允許並升級**] 與 [**封鎖並升級**選項時，用戶端會收到更新的軟體，從 Windows Server 更新服務 （如果您正在使用這項服務） 或 Microsoft Update。</span><span class="sxs-lookup"><span data-stu-id="e66e0-107">When you set a client version policy and use the options **Allow and upgrade** and **Block and upgrade**, clients will receive updated software from the Windows Server Update Service (if you are using this service) or from Microsoft Update.</span></span>

<div>

## <a name="client-version-policy-settings"></a><span data-ttu-id="e66e0-108">用戶端版本原則設定</span><span class="sxs-lookup"><span data-stu-id="e66e0-108">Client Version Policy Settings</span></span>

<span data-ttu-id="e66e0-109">預設用戶端版本原則需要所有用戶端執行 Lync。</span><span class="sxs-lookup"><span data-stu-id="e66e0-109">The default client version policy requires that all clients run Lync.</span></span> <span data-ttu-id="e66e0-110">如果您的環境中的用戶端執行舊版 Communicator，您可能需要重新設定用戶端版本規則，以避免用戶端和裝置的意外封鎖或更新連線至 Lync Server 2013 時。</span><span class="sxs-lookup"><span data-stu-id="e66e0-110">If clients in your environment are running earlier versions of Communicator, you may need to reconfigure the Client Version rules to prevent clients and devices from being unexpectedly blocked or updated when connecting to Lync Server 2013.</span></span> <span data-ttu-id="e66e0-111">您可以修改預設規則，或者您可以在用戶端版本原則清單中，若要覆寫預設規則新增較高的規則。</span><span class="sxs-lookup"><span data-stu-id="e66e0-111">You can modify the default rule, or you can add a rule higher in the Client Version Policy list to override the default rule.</span></span> <span data-ttu-id="e66e0-112">此外，當發行累積更新 (Cu)，您應該設定為需要最新的更新用戶端版本原則。</span><span class="sxs-lookup"><span data-stu-id="e66e0-112">Additionally, as Cumulative Updates (CUs) are released, you should configure the Client Version Policy to require the latest updates.</span></span> <span data-ttu-id="e66e0-113">如需詳細資訊，請參閱作業文件中的[指定，可以用來登入 Lync Server 2013 的用戶端應用程式](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="e66e0-113">For details, see [Specifying the client applications that can be used to log on to Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md) in the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013：有關 Lync On Lync-Skype connectivity 的注意事項
description: Lync Server 2013：有關 Lync On 的 Lync-Skype 連線資訊，請注意。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Note about Lync-Skype connectivity for Lync On
ms:assetid: 1d0f5c1a-74c6-468f-9877-ad2b1ddf355f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440169(v=OCS.15)
ms:contentKeyID: 57793359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f7d9758f277f2f987677c2c0ffa0a4447ba31d1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579199"
---
# <a name="note-about-lync-skype-connectivity-in-lync-server-2013-for-lync-online-customers"></a><span data-ttu-id="a1ef1-103">有關 Lync Online 客戶在 Lync Server 2013 中 Lync-Skype 連線的附注</span><span class="sxs-lookup"><span data-stu-id="a1ef1-103">Note about Lync-Skype connectivity in Lync Server 2013 for Lync Online customers</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1ef1-104">_**主題上次修改日期：** 2013-09-23_</span><span class="sxs-lookup"><span data-stu-id="a1ef1-104">_**Topic Last Modified:** 2013-09-23_</span></span>

<span data-ttu-id="a1ef1-105">這份檔已撰寫，可協助設定 Lync Server 內部部署管理員 Lync-Skype 連線能力。</span><span class="sxs-lookup"><span data-stu-id="a1ef1-105">This document was written to help Lync Server on-premise administrators set up Lync-Skype connectivity.</span></span><span data-ttu-id="a1ef1-106">Lync-Skype 連線也是 Lync Online 的一項功能，也就是 Office 365 和 Microsoft 365 的一部分。</span><span class="sxs-lookup"><span data-stu-id="a1ef1-106">  Lync-Skype connectivity is also a feature of Lync Online, which is part of Office 365 and Microsoft 365.</span></span> <span data-ttu-id="a1ef1-107">您可以從系統管理中心內的 Lync 系統管理中心啟用 Lync-Skype connectivity 功能。</span><span class="sxs-lookup"><span data-stu-id="a1ef1-107">You can enable the Lync-Skype connectivity feature from the Lync Administration Center within the admin center.</span></span>

<span data-ttu-id="a1ef1-108">Microsoft 365 中型企業版、Office 365 企業版、Microsoft 365 教育版和 Office 365 for 政府：登入 Office 365 入口網站或 Microsoft 365 系統管理中心，並流覽至 **Lync 系統管理中心**。</span><span class="sxs-lookup"><span data-stu-id="a1ef1-108">For Microsoft 365 Midsize Business, Office 365 Enterprise, Microsoft 365 Education, and Office 365 for Government: Sign in to the Office 365 portal or Microsoft 365 admin center and navigate to the **Lync Administration Center**.</span></span> <span data-ttu-id="a1ef1-109">移至 [ **外部通訊**]。</span><span class="sxs-lookup"><span data-stu-id="a1ef1-109">Go to **External Communications**.</span></span> <span data-ttu-id="a1ef1-110">在 [ **公用 IM 服務提供者**] 底下，按一下 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="a1ef1-110">Under **Public IM Service Providers**, click **Enable**.</span></span> <span data-ttu-id="a1ef1-111">如果您想要控制個別使用者對 Lync-Skype 連線的存取，您可以編輯個別使用者的外部通訊設定來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="a1ef1-111">If you want to control individual user access to Lync-Skype Connectivity, you can do so by editing individual users’ External Communications settings.</span></span>

<span data-ttu-id="a1ef1-112">Microsoft 365 Small Business Premium：登入 Microsoft 365，然後移至 **Admin \> 服務設定 \> 立即訊息、會議和會議**。</span><span class="sxs-lookup"><span data-stu-id="a1ef1-112">For Microsoft 365 Small Business Premium: Sign in to Microsoft 365, and go to **Admin \> Service Settings \> Instant messaging, meetings and conferencing**.</span></span> <span data-ttu-id="a1ef1-113">開啟外部通訊。</span><span class="sxs-lookup"><span data-stu-id="a1ef1-113">Turn on External communications.</span></span> <span data-ttu-id="a1ef1-114">外部通訊參數會同時開啟 Lync-Skype 連線，以及與使用 Lync 的其他組織進行通訊。</span><span class="sxs-lookup"><span data-stu-id="a1ef1-114">The External communications switch turns on both Lync-Skype connectivity and communications with other organizations that use Lync.</span></span> <span data-ttu-id="a1ef1-115">視您開始使用 Lync Online 的時間而定，「on」狀態的外部通訊切換器最初可能只會指出與其他 Lync 組織的通訊已啟用。</span><span class="sxs-lookup"><span data-stu-id="a1ef1-115">Depending on when you started using Lync Online, the External communications switch in an "on" state may initially indicate only that communications with other Lync organizations is activated.</span></span> <span data-ttu-id="a1ef1-116">若要開啟 Lync-Skype 連線能力，只要關閉開關，然後再重新開啟即可。</span><span class="sxs-lookup"><span data-stu-id="a1ef1-116">To turn on Lync-Skype Connectivity, simply toggle the switch off and then back on again.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


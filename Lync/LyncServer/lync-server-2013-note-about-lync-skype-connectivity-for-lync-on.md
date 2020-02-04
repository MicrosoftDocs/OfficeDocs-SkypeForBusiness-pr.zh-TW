---
title: Lync Server 2013： lync 的 lync-Skype 連線的相關注意事項
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
ms.openlocfilehash: 053c29573ccac6a67473db8ba46b80cf1cdf3dcc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755837"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="note-about-lync-skype-connectivity-in-lync-server-2013-for-lync-online-customers"></a><span data-ttu-id="404e6-102">有關 lync Online 客戶的 lync Server 2013 中的 Lync-Skype 連線性注意事項</span><span class="sxs-lookup"><span data-stu-id="404e6-102">Note about Lync-Skype connectivity in Lync Server 2013 for Lync Online customers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="404e6-103">_**主題上次修改日期：** 2013-09-23_</span><span class="sxs-lookup"><span data-stu-id="404e6-103">_**Topic Last Modified:** 2013-09-23_</span></span>

<span data-ttu-id="404e6-104">此檔是為協助 Lync Server 內部部署系統管理員設定 Lync-Skype 連線性所撰寫。</span><span class="sxs-lookup"><span data-stu-id="404e6-104">This document was written to help Lync Server on-premise administrators set up Lync-Skype connectivity.</span></span><span data-ttu-id="404e6-105">Lync Online 也是 Lync Online 的一項功能，也就是 Office 365 的一部分。</span><span class="sxs-lookup"><span data-stu-id="404e6-105">  Lync-Skype connectivity is also a feature of Lync Online, which is part of Office 365.</span></span> <span data-ttu-id="404e6-106">您可以從 Office 365 入口網站中的 Lync 系統管理中心啟用 Lync-Skype 連線功能。</span><span class="sxs-lookup"><span data-stu-id="404e6-106">You can enable the Lync-Skype connectivity feature from the Lync Administration Center within the Office 365 portal.</span></span>

<span data-ttu-id="404e6-107">針對 Office 365 中型企業版、Office 365 Enterprise、Office 365 教育版，以及適用于政府的 Office 365：登入 Office 365 入口網站，然後流覽至**Lync 系統管理中心**。</span><span class="sxs-lookup"><span data-stu-id="404e6-107">For Office 365 Midsize Business, Office 365 Enterprise, Office 365 Education, and Office 365 for Government: Sign in to the Office 365 portal and navigate to the **Lync Administration Center**.</span></span> <span data-ttu-id="404e6-108">移至 [**外部通訊**]。</span><span class="sxs-lookup"><span data-stu-id="404e6-108">Go to **External Communications**.</span></span> <span data-ttu-id="404e6-109">在 [**公用 IM 服務提供者**] 底下，按一下 [**啟用**]。</span><span class="sxs-lookup"><span data-stu-id="404e6-109">Under **Public IM Service Providers**, click **Enable**.</span></span> <span data-ttu-id="404e6-110">如果您想要控制個別使用者對 Lync 與 Skype 連線的存取權，您可以編輯個別使用者的 [外部通訊] 設定來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="404e6-110">If you want to control individual user access to Lync-Skype Connectivity, you can do so by editing individual users’ External Communications settings.</span></span>

<span data-ttu-id="404e6-111">針對 Office 365 小型企業版 Premium：登入 Office 365，然後移至 **[ \>管理員服務\>設定立即訊息、會議和會議**]。</span><span class="sxs-lookup"><span data-stu-id="404e6-111">For Office 365 Small Business Premium: Sign in to Office 365, and go to **Admin \> Service Settings \> Instant messaging, meetings and conferencing**.</span></span> <span data-ttu-id="404e6-112">開啟 [外部通訊]。</span><span class="sxs-lookup"><span data-stu-id="404e6-112">Turn on External communications.</span></span> <span data-ttu-id="404e6-113">外部通訊開關會開啟 Lync Skype 連線的連線，以及與使用 Lync 的其他組織進行通訊。</span><span class="sxs-lookup"><span data-stu-id="404e6-113">The External communications switch turns on both Lync-Skype connectivity and communications with other organizations that use Lync.</span></span> <span data-ttu-id="404e6-114">根據您開始使用 Lync Online 的時間而定，「開啟」狀態的外部通訊開關最初可能只會指出與其他 Lync 組織的通訊已啟用。</span><span class="sxs-lookup"><span data-stu-id="404e6-114">Depending on when you started using Lync Online, the External communications switch in an "on" state may initially indicate only that communications with other Lync organizations is activated.</span></span> <span data-ttu-id="404e6-115">若要開啟 Lync Skype 連線，只要關閉並再次開啟交換器，然後再重新開啟。</span><span class="sxs-lookup"><span data-stu-id="404e6-115">To turn on Lync-Skype Connectivity, simply toggle the switch off and then back on again.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


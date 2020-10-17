---
title: Lync Server 2013：管理組織的 XMPP 同盟夥伴
description: Lync Server 2013：管理組織的 XMPP 同盟合作夥伴。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage XMPP federated partners for your organization
ms:assetid: 48681433-725d-457f-926b-f91d95bcf082
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552450(v=OCS.15)
ms:contentKeyID: 48679561
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37d6fb4104c35ffc7db9649656f7786568a48b61
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556692"
---
# <a name="manage-xmpp-federated-partners-in-lync-server-2013"></a><span data-ttu-id="dc6ac-103">在 Lync Server 2013 中管理 XMPP 同盟協力廠商</span><span class="sxs-lookup"><span data-stu-id="dc6ac-103">Manage XMPP federated partners in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc6ac-104">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="dc6ac-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="dc6ac-105">這是初步檔，而且可能會變更。</span><span class="sxs-lookup"><span data-stu-id="dc6ac-105">This is preliminary documentation and is subject to change.</span></span> <span data-ttu-id="dc6ac-106">空白主題會以預留位置形式包含。</span><span class="sxs-lookup"><span data-stu-id="dc6ac-106">Blank topics are included as placeholders.</span></span>

<span data-ttu-id="dc6ac-107">若要管理 XMPP 同盟網域使用者的支援，您需要執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="dc6ac-107">To manage support for users of XMPP federated domains, you need to do the following:</span></span>

  - <span data-ttu-id="dc6ac-108">設定一個或多個外部存取原則，以支援 XMPP 同盟網域的使用者。</span><span class="sxs-lookup"><span data-stu-id="dc6ac-108">Configure one or more external access policies to support users of XMPP federated domains.</span></span>

  - <span data-ttu-id="dc6ac-109">設定「Access Edge 設定」原則以支援同盟。</span><span class="sxs-lookup"><span data-stu-id="dc6ac-109">Configure Access Edge Configuration policy to support federation.</span></span>

  - <span data-ttu-id="dc6ac-110">建立 XMPP 同盟協力廠商定義。</span><span class="sxs-lookup"><span data-stu-id="dc6ac-110">Create XMPP Federated Partners definitions.</span></span>

  - <span data-ttu-id="dc6ac-111">了解 XMPP 同盟可使用的交涉設定。</span><span class="sxs-lookup"><span data-stu-id="dc6ac-111">Understand negotiation settings available for XMPP federation.</span></span>

<span data-ttu-id="dc6ac-112">若要執行這些工作，請使用本節中的程式。</span><span class="sxs-lookup"><span data-stu-id="dc6ac-112">To perform these tasks, use the procedures in this section.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="dc6ac-113">本章節內容</span><span class="sxs-lookup"><span data-stu-id="dc6ac-113">In This Section</span></span>

  - [<span data-ttu-id="dc6ac-114">在 Lync Server 2013 中建立或編輯 XMPP partner configuration</span><span class="sxs-lookup"><span data-stu-id="dc6ac-114">Create or edit XMPP partner configuration in Lync Server 2013</span></span>](lync-server-2013-create-or-edit-xmpp-partner-configuration.md)

  - [<span data-ttu-id="dc6ac-115">Lync Server 2013 中 XMPP 同盟合作夥伴的協商設定</span><span class="sxs-lookup"><span data-stu-id="dc6ac-115">Negotiation settings for XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)

  - [<span data-ttu-id="dc6ac-116">Lync Server 2013 的範例 XMPP 設定– XMPP 與 Google 交談的同盟</span><span class="sxs-lookup"><span data-stu-id="dc6ac-116">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


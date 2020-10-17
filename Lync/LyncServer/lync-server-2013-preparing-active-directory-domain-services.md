---
title: Lync Server 2013：準備 Active Directory 網域服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing Active Directory Domain Services for Lync Server 2013
ms:assetid: 7e126464-5d29-4013-9c44-0ccc2fbdea0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398630(v=OCS.15)
ms:contentKeyID: 48184620
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc8b5f4a5efc60456d874276b025ff7ca9806028
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513310"
---
# <a name="preparing-active-directory-domain-services-for-lync-server-2013"></a><span data-ttu-id="47285-102">為 Lync Server 2013 準備 Active Directory 網域服務</span><span class="sxs-lookup"><span data-stu-id="47285-102">Preparing Active Directory Domain Services for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47285-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="47285-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="47285-104">在您部署及操作 Lync Server 2013 之前，您必須先擴充架構，然後建立及設定物件，以準備 Active Directory 網域服務。</span><span class="sxs-lookup"><span data-stu-id="47285-104">Before you deploy and operate Lync Server 2013, you must prepare Active Directory Domain Services by extending the schema and then creating and configuring objects.</span></span> <span data-ttu-id="47285-105">架構擴充新增 Lync Server 所需的 Active Directory 類別和屬性。</span><span class="sxs-lookup"><span data-stu-id="47285-105">The schema extensions add the Active Directory classes and attributes that are required by Lync Server.</span></span>

<span data-ttu-id="47285-106">本節中的主題說明如何準備用於部署 Lync Server 的 AD DS，以及如何指派安裝和組織單位 (OU) 許可權。</span><span class="sxs-lookup"><span data-stu-id="47285-106">The topics in this section describe how to prepare AD DS for deploying Lync Server and how to assign setup and organizational unit (OU) permissions.</span></span> <span data-ttu-id="47285-107">如需 Lync Server 所需之架構變更的詳細資訊，請參閱 [Lync server 2013 所使用的 Active Directory 架構擴充功能、類別和屬性](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)。</span><span class="sxs-lookup"><span data-stu-id="47285-107">For details about the schema changes required for Lync Server, see [Active Directory schema extensions, classes, and attributes used by Lync Server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="47285-108">本章節內容</span><span class="sxs-lookup"><span data-stu-id="47285-108">In This Section</span></span>

  - [<span data-ttu-id="47285-109">Lync Server 2013 的 Active Directory 基礎結構需求</span><span class="sxs-lookup"><span data-stu-id="47285-109">Active Directory infrastructure requirements for Lync Server 2013</span></span>](lync-server-2013-active-directory-infrastructure-requirements.md)

  - [<span data-ttu-id="47285-110">Lync Server 2013 中的 Active Directory 網域服務準備工作</span><span class="sxs-lookup"><span data-stu-id="47285-110">Overview of Active Directory Domain Services preparation in Lync Server 2013</span></span>](lync-server-2013-overview-of-active-directory-domain-services-preparation.md)

  - [<span data-ttu-id="47285-111">在 Lync Server 2013 中準備 Active Directory 網域服務</span><span class="sxs-lookup"><span data-stu-id="47285-111">Preparing Active Directory Domain Services in Lync Server 2013</span></span>](lync-server-2013-preparing-active-directory-domain-services_1.md)

  - [<span data-ttu-id="47285-112">在 Lync Server 2013 中準備鎖定的 Active Directory 網域服務</span><span class="sxs-lookup"><span data-stu-id="47285-112">Preparing a locked-down Active Directory Domain Services in Lync Server 2013</span></span>](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)

  - [<span data-ttu-id="47285-113">在 Lync Server 2013 中授與許可權</span><span class="sxs-lookup"><span data-stu-id="47285-113">Granting permissions in Lync Server 2013</span></span>](lync-server-2013-granting-permissions.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013： 準備 Active Directory 網域服務
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
ms.openlocfilehash: 4deedc7a3913a33ad6524a8eab4dd3f66ba961b3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208799"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-active-directory-domain-services-for-lync-server-2013"></a><span data-ttu-id="025f5-102">為 Lync Server 2013 準備 Active Directory 網域服務</span><span class="sxs-lookup"><span data-stu-id="025f5-102">Preparing Active Directory Domain Services for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="025f5-103">_**上次修改主題：** 2013年-02-21_</span><span class="sxs-lookup"><span data-stu-id="025f5-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="025f5-104">您部署及操作 Lync Server 2013 之前，您必須準備 Active Directory 網域服務延伸架構和再建立及設定的物件。</span><span class="sxs-lookup"><span data-stu-id="025f5-104">Before you deploy and operate Lync Server 2013, you must prepare Active Directory Domain Services by extending the schema and then creating and configuring objects.</span></span> <span data-ttu-id="025f5-105">架構延伸模組新增的 Active Directory 類別和 Lync Server 所需的屬性。</span><span class="sxs-lookup"><span data-stu-id="025f5-105">The schema extensions add the Active Directory classes and attributes that are required by Lync Server.</span></span>

<span data-ttu-id="025f5-106">本節中的主題說明如何先準備 AD DS 部署 Lync Server，以及如何指派設定和組織單位 (OU) 權限。</span><span class="sxs-lookup"><span data-stu-id="025f5-106">The topics in this section describe how to prepare AD DS for deploying Lync Server and how to assign setup and organizational unit (OU) permissions.</span></span> <span data-ttu-id="025f5-107">如需 Lync Server 所需的架構變更的詳細資訊，請參閱[Active Directory 架構延伸模組、 類別及 Lync Server 2013 所使用的屬性](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)。</span><span class="sxs-lookup"><span data-stu-id="025f5-107">For details about the schema changes required for Lync Server, see [Active Directory schema extensions, classes, and attributes used by Lync Server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="025f5-108">本章節內容</span><span class="sxs-lookup"><span data-stu-id="025f5-108">In This Section</span></span>

  - [<span data-ttu-id="025f5-109">Lync Server 2013 的 active Directory 基礎結構需求</span><span class="sxs-lookup"><span data-stu-id="025f5-109">Active Directory infrastructure requirements for Lync Server 2013</span></span>](lync-server-2013-active-directory-infrastructure-requirements.md)

  - [<span data-ttu-id="025f5-110">Lync Server 2013 中的 Active Directory 網域服務準備的概觀</span><span class="sxs-lookup"><span data-stu-id="025f5-110">Overview of Active Directory Domain Services preparation in Lync Server 2013</span></span>](lync-server-2013-overview-of-active-directory-domain-services-preparation.md)

  - [<span data-ttu-id="025f5-111">準備 Lync Server 2013 中的 Active Directory 網域服務</span><span class="sxs-lookup"><span data-stu-id="025f5-111">Preparing Active Directory Domain Services in Lync Server 2013</span></span>](lync-server-2013-preparing-active-directory-domain-services_1.md)

  - [<span data-ttu-id="025f5-112">準備鎖定的 Active Directory 網域服務在 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="025f5-112">Preparing a locked-down Active Directory Domain Services in Lync Server 2013</span></span>](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)

  - [<span data-ttu-id="025f5-113">授與 Lync Server 2013 中的權限</span><span class="sxs-lookup"><span data-stu-id="025f5-113">Granting permissions in Lync Server 2013</span></span>](lync-server-2013-granting-permissions.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


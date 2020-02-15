---
title: Lync Server 2013： 更新 Outlook 啟用清單
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Updating the Outlook enable list
ms:assetid: 5db120dc-52f9-4dde-acb9-3824ae245086
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215438(v=OCS.15)
ms:contentKeyID: 48242739
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 376c5788d535cd893b2261dcddcb1fe05d676005
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007662"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="updating-the-outlook-enable-list-in-lync-server-2013"></a><span data-ttu-id="c69a4-102">更新 Lync Server 2013 中的 Outlook 啟用清單</span><span class="sxs-lookup"><span data-stu-id="c69a4-102">Updating the Outlook enable list in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c69a4-103">_**上次修改主題：** 2013年-01-07_</span><span class="sxs-lookup"><span data-stu-id="c69a4-103">_**Topic Last Modified:** 2013-01-07_</span></span>

<span data-ttu-id="c69a4-104">您可以確保，Online Meeting add-in for Microsoft Lync 2013 永遠保持啟用的使用者所建立的原則，包括其增益集管理清單中的 Outlook。</span><span class="sxs-lookup"><span data-stu-id="c69a4-104">You can ensure that Online Meeting Add-in for Microsoft Lync 2013 always remains enabled for users by creating a policy that includes it in the Add-in Management List for Outlook.</span></span> <span data-ttu-id="c69a4-105">「增益集管理清單」原則包含在「群組原則管理主控台」的 Office 系統管理範本檔案中。</span><span class="sxs-lookup"><span data-stu-id="c69a4-105">The Add-in Management List policy is included in the Office administrative template files for the Group Policy Management Console.</span></span> <span data-ttu-id="c69a4-106">它會建立登錄機碼下 HKCU\\軟體\\原則\\Microsoft\\Office\\15.0\\Outlook15\\Resiliency\\AddinList。</span><span class="sxs-lookup"><span data-stu-id="c69a4-106">It creates a registry key under HKCU\\Software\\Policies\\Microsoft\\Office\\15.0\\Outlook15\\Resiliency\\AddinList.</span></span> <span data-ttu-id="c69a4-107">您可以 ucaddin.dll 值加入此機碼，並設定 ucaddin.dll 值，使它一律會啟用，以便讓使用者無法手動予以停用</span><span class="sxs-lookup"><span data-stu-id="c69a4-107">You can add a value for the ucaddin.dll to this key, and configure the ucaddin.dll value so that it is always enabled and so that users cannot manually disable it</span></span>

<div>

## <a name="to-add-ucaddindll-to-the-outlook-add-in-list"></a><span data-ttu-id="c69a4-108">若要將 ucaddin.dll 新增至 Outlook 增益集清單</span><span class="sxs-lookup"><span data-stu-id="c69a4-108">To Add ucaddin.dll to the Outlook Add-in List</span></span>

  - <span data-ttu-id="c69a4-109">AddinList 登錄機碼，位於 [HKCU\\軟體\\原則\\Microsoft\\Office\\15.0\\Outlook15\\Resiliency\\AddinList，新增下列值：</span><span class="sxs-lookup"><span data-stu-id="c69a4-109">To the AddinList registry key, located under HKCU\\Software\\Policies\\Microsoft\\Office\\15.0\\Outlook15\\Resiliency\\AddinList, add the following value:</span></span>
    
      - <span data-ttu-id="c69a4-110">登錄類型 = 登錄\_Linkid</span><span class="sxs-lookup"><span data-stu-id="c69a4-110">Registry Type = REG\_SZ</span></span>
    
      - <span data-ttu-id="c69a4-111">名稱 = ucaddin.dll</span><span class="sxs-lookup"><span data-stu-id="c69a4-111">Name = ucaddin.dll</span></span>
    
      - <span data-ttu-id="c69a4-112">值 = 1 (指定增益集一律啟用，而且使用者無法管理)</span><span class="sxs-lookup"><span data-stu-id="c69a4-112">Value = 1 (specifies that the add-in is always enabled and cannot be managed by the end user)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


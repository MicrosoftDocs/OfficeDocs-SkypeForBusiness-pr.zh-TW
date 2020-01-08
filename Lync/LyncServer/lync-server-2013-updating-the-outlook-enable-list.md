---
title: Lync Server 2013：更新 Outlook 啟用清單
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Updating the Outlook enable list
ms:assetid: 5db120dc-52f9-4dde-acb9-3824ae245086
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215438(v=OCS.15)
ms:contentKeyID: 48242739
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20c7ee75e70b52a4edd01230fe10aeb46f6e6e40
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975483"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="updating-the-outlook-enable-list-in-lync-server-2013"></a><span data-ttu-id="8b9b1-102">更新 Lync Server 2013 中的 Outlook 啟用清單</span><span class="sxs-lookup"><span data-stu-id="8b9b1-102">Updating the Outlook enable list in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b9b1-103">_**主題上次修改日期：** 2013-01-07_</span><span class="sxs-lookup"><span data-stu-id="8b9b1-103">_**Topic Last Modified:** 2013-01-07_</span></span>

<span data-ttu-id="8b9b1-104">您可以在 Outlook 的增益集管理清單中建立一個策略，以確保 Microsoft Lync 2013 的 [線上會議] 增益集能一直保持為使用者啟用。</span><span class="sxs-lookup"><span data-stu-id="8b9b1-104">You can ensure that Online Meeting Add-in for Microsoft Lync 2013 always remains enabled for users by creating a policy that includes it in the Add-in Management List for Outlook.</span></span> <span data-ttu-id="8b9b1-105">增益集管理清單原則包含在群群組原則管理主控台的 Office 系統管理範本檔案中。</span><span class="sxs-lookup"><span data-stu-id="8b9b1-105">The Add-in Management List policy is included in the Office administrative template files for the Group Policy Management Console.</span></span> <span data-ttu-id="8b9b1-106">它會在\\[HKCU 軟體\\策略\\] 下，\\建立\\Microsoft\\Office\\15.0\\Outlook15 復原 AddinList 的登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="8b9b1-106">It creates a registry key under HKCU\\Software\\Policies\\Microsoft\\Office\\15.0\\Outlook15\\Resiliency\\AddinList.</span></span> <span data-ttu-id="8b9b1-107">您可以將 ucaddin 的值加到此索引鍵，並設定 ucaddin 的值，讓使用者不能手動將它停用。</span><span class="sxs-lookup"><span data-stu-id="8b9b1-107">You can add a value for the ucaddin.dll to this key, and configure the ucaddin.dll value so that it is always enabled and so that users cannot manually disable it</span></span>

<div>

## <a name="to-add-ucaddindll-to-the-outlook-add-in-list"></a><span data-ttu-id="8b9b1-108">若要將 ucaddin 新增至 Outlook 增益集清單</span><span class="sxs-lookup"><span data-stu-id="8b9b1-108">To Add ucaddin.dll to the Outlook Add-in List</span></span>

  - <span data-ttu-id="8b9b1-109">在 AddinList 登錄機碼（位於 [HKCU\\軟體\\原則\\]\\底下\\的\\[\\Microsoft\\Office 15.0 Outlook15 復原 AddinList] 中，新增下列值：</span><span class="sxs-lookup"><span data-stu-id="8b9b1-109">To the AddinList registry key, located under HKCU\\Software\\Policies\\Microsoft\\Office\\15.0\\Outlook15\\Resiliency\\AddinList, add the following value:</span></span>
    
      - <span data-ttu-id="8b9b1-110">註冊表類型 = REG\_SZ</span><span class="sxs-lookup"><span data-stu-id="8b9b1-110">Registry Type = REG\_SZ</span></span>
    
      - <span data-ttu-id="8b9b1-111">Name = ucaddin</span><span class="sxs-lookup"><span data-stu-id="8b9b1-111">Name = ucaddin.dll</span></span>
    
      - <span data-ttu-id="8b9b1-112">值 = 1 （指定該增益集永遠啟用，且無法由最終使用者管理）</span><span class="sxs-lookup"><span data-stu-id="8b9b1-112">Value = 1 (specifies that the add-in is always enabled and cannot be managed by the end user)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


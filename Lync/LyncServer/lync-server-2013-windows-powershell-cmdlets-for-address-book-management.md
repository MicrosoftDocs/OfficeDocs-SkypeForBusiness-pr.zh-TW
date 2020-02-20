---
title: '適用於通訊錄管理的 Lync Server 2013: Windows PowerShell cmdlet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Windows PowerShell cmdlets for Address Book management
ms:assetid: 73bfa949-5628-4156-ad20-fe07a0dc6216
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429708(v=OCS.15)
ms:contentKeyID: 48184512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3190e6b3727d1d226a217dc059a1f0b69f890a16
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149062"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="windows-powershell-cmdlets-for-address-book-services-in-lync-server-2013"></a><span data-ttu-id="3ce36-102">Lync Server 2013 中通訊錄服務的 Windows PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="3ce36-102">Windows PowerShell cmdlets for Address Book Services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ce36-103">_**主題上次修改日期：** 2012年-11-01_</span><span class="sxs-lookup"><span data-stu-id="3ce36-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3ce36-104">Lync Server 提供數個 Windows PowerShell 命令列介面 cmdlet 來管理及設定通訊錄服務。</span><span class="sxs-lookup"><span data-stu-id="3ce36-104">Lync Server provides a number of Windows PowerShell command-line interface cmdlets to manage and configure the Address Book service.</span></span> <span data-ttu-id="3ce36-105">這些 cmdlet 的某些是取代的舊版 Office Communications Server 中使用的 ABServer.exe 命令。</span><span class="sxs-lookup"><span data-stu-id="3ce36-105">Some of these cmdlets are replacements for the ABServer.exe commands used in previous versions of Office Communications Server.</span></span> <span data-ttu-id="3ce36-106">下列主題中的 Cmdlet 是用來設定、建立及擷取通訊錄服務資訊、其設定，以及通訊錄服務在用戶端擷取通訊錄服務檔案及設定時使用的 Web 服務資訊。</span><span class="sxs-lookup"><span data-stu-id="3ce36-106">In the following topics are the cmdlets that are used to set, create, and retrieve information about the Address Book service, its configuration and information about the Web services that the Address Book service uses when clients retrieve Address Book service files and settings.</span></span>

<span data-ttu-id="3ce36-107">所有這些 cmdlet 會發出透過位於系統管理工具中已安裝所在的伺服器或工作站上的 Lync Server 工具在 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="3ce36-107">All of these cmdlets are issued through the Lync Server Management Shell found in the Lync Server tools on a server or workstation where the administration tools have been installed.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3ce36-108">本章節內容</span><span class="sxs-lookup"><span data-stu-id="3ce36-108">In This Section</span></span>

  - [<span data-ttu-id="3ce36-109">New-csaddressbookconfiguration 適用於 Lync Server 2013 中的 Address Book 管理</span><span class="sxs-lookup"><span data-stu-id="3ce36-109">New-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-New-CsAddressBookConfiguration-for-address-book-management.md)

  - [<span data-ttu-id="3ce36-110">設定 CsAddressBookConfiguration 適用於 Lync Server 2013 中的 Address Book 管理</span><span class="sxs-lookup"><span data-stu-id="3ce36-110">Set-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-set-csaddressbookconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="3ce36-111">Get-csaddressbookconfiguration cmdlet 適用於 Lync Server 2013 中的 Address Book 管理</span><span class="sxs-lookup"><span data-stu-id="3ce36-111">Get-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-get-csaddressbookconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="3ce36-112">移除 CsAddressBookConfiguration 適用於 Lync Server 2013 中的 Address Book 管理</span><span class="sxs-lookup"><span data-stu-id="3ce36-112">Remove-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-remove-csaddressbookconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="3ce36-113">適用於通訊錄管理 Lync Server 2013 中的測試 CsAddressBookService</span><span class="sxs-lookup"><span data-stu-id="3ce36-113">Test-CsAddressBookService for Address Book management in Lync Server 2013</span></span>](lync-server-2013-test-csaddressbookservice-for-address-book-management.md)

  - [<span data-ttu-id="3ce36-114">適用於通訊錄管理 Lync Server 2013 中的測試 CsAddressBookWebQuery</span><span class="sxs-lookup"><span data-stu-id="3ce36-114">Test-CsAddressBookWebQuery for Address Book management in Lync Server 2013</span></span>](lync-server-2013-test-csaddressbookwebquery-for-address-book-management.md)

  - [<span data-ttu-id="3ce36-115">適用於 Lync Server 2013 中的通訊錄管理的 Update-csaddressbook</span><span class="sxs-lookup"><span data-stu-id="3ce36-115">Update-CsAddressBook for Address Book management in Lync Server 2013</span></span>](lync-server-2013-update-csaddressbook-for-address-book-management.md)

  - [<span data-ttu-id="3ce36-116">適用於通訊錄管理 Lync Server 2013 中的新 CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="3ce36-116">New-CsClientPolicy for Address Book management in Lync Server 2013</span></span>](lync-server-2013-new-csclientpolicy-for-address-book-management.md)

  - [<span data-ttu-id="3ce36-117">適用於 Lync Server 2013 中的通訊錄管理的 Set-csclientpolicy</span><span class="sxs-lookup"><span data-stu-id="3ce36-117">Set-CsClientPolicy for Address Book management in Lync Server 2013</span></span>](lync-server-2013-set-csclientpolicy-for-address-book-management.md)

  - [<span data-ttu-id="3ce36-118">適用於通訊錄管理 Lync Server 2013 中的 get-CsService</span><span class="sxs-lookup"><span data-stu-id="3ce36-118">Get-CsService for Address Book management in Lync Server 2013</span></span>](lync-server-2013-get-csservice-for-address-book-management.md)

  - [<span data-ttu-id="3ce36-119">適用於通訊錄管理 Lync Server 2013 中的新 CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="3ce36-119">New-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-New-CsWebServiceConfiguration-for-address-book-management.md)

  - [<span data-ttu-id="3ce36-120">適用於通訊錄管理 Lync Server 2013 中的 get-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="3ce36-120">Get-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-get-cswebserviceconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="3ce36-121">設定 CsWebServiceConfiguration 適用於 Lync Server 2013 中的 Address Book 管理</span><span class="sxs-lookup"><span data-stu-id="3ce36-121">Set-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-set-cswebserviceconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="3ce36-122">移除 CsWebServiceConfiguration 適用於 Lync Server 2013 中的 Address Book 管理</span><span class="sxs-lookup"><span data-stu-id="3ce36-122">Remove-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-remove-cswebserviceconfiguration-for-address-book-management.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="3ce36-123">相關章節</span><span class="sxs-lookup"><span data-stu-id="3ce36-123">Related Sections</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3ce36-124">請參閱</span><span class="sxs-lookup"><span data-stu-id="3ce36-124">See Also</span></span>


[https://go.microsoft.com/fwlink/p/?linkId=205826](https://go.microsoft.com/fwlink/p/?linkid=205826)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


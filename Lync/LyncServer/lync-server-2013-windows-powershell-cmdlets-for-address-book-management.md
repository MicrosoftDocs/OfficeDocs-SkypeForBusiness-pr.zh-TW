---
title: Lync Server 2013：適用于通訊錄管理的 Windows PowerShell Cmdlet
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
ms.openlocfilehash: 170936c8ca4445a7dc4e816c2300176d9b730f80
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535320"
---
# <a name="windows-powershell-cmdlets-for-address-book-services-in-lync-server-2013"></a><span data-ttu-id="d4b7e-102">Lync Server 2013 中的通訊錄服務的 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="d4b7e-102">Windows PowerShell cmdlets for Address Book Services in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4b7e-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="d4b7e-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="d4b7e-104">Lync Server 提供許多 Windows PowerShell 命令列介面 Cmdlet 來管理及設定通訊錄服務。</span><span class="sxs-lookup"><span data-stu-id="d4b7e-104">Lync Server provides a number of Windows PowerShell command-line interface cmdlets to manage and configure the Address Book service.</span></span> <span data-ttu-id="d4b7e-105">在舊版 Office 通訊伺服器中使用的 ABServer.exe 命令，會取代這些 Cmdlet 中的某些 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d4b7e-105">Some of these cmdlets are replacements for the ABServer.exe commands used in previous versions of Office Communications Server.</span></span> <span data-ttu-id="d4b7e-106">下列主題中的 Cmdlet 是用來設定、建立及擷取通訊錄服務資訊、其設定，以及通訊錄服務在用戶端擷取通訊錄服務檔案及設定時使用的 Web 服務資訊。</span><span class="sxs-lookup"><span data-stu-id="d4b7e-106">In the following topics are the cmdlets that are used to set, create, and retrieve information about the Address Book service, its configuration and information about the Web services that the Address Book service uses when clients retrieve Address Book service files and settings.</span></span>

<span data-ttu-id="d4b7e-107">所有的指令程式都是透過在已安裝管理工具之伺服器或工作站上的 Lync server 工具中找到的 Lync Server 管理命令介面來發出。</span><span class="sxs-lookup"><span data-stu-id="d4b7e-107">All of these cmdlets are issued through the Lync Server Management Shell found in the Lync Server tools on a server or workstation where the administration tools have been installed.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d4b7e-108">本章節內容</span><span class="sxs-lookup"><span data-stu-id="d4b7e-108">In This Section</span></span>

  - [<span data-ttu-id="d4b7e-109">Lync Server 2013 中用於通訊錄管理的 New-CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="d4b7e-109">New-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-New-CsAddressBookConfiguration-for-address-book-management.md)

  - [<span data-ttu-id="d4b7e-110">Lync Server 2013 中用於通訊錄管理的 Set-CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="d4b7e-110">Set-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-set-csaddressbookconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="d4b7e-111">Lync Server 2013 中用於通訊錄管理的 Get-CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="d4b7e-111">Get-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-get-csaddressbookconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="d4b7e-112">Lync Server 2013 中用於通訊錄管理的 Remove-CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="d4b7e-112">Remove-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-remove-csaddressbookconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="d4b7e-113">Lync Server 2013 中用於通訊錄管理的 Test-CsAddressBookService</span><span class="sxs-lookup"><span data-stu-id="d4b7e-113">Test-CsAddressBookService for Address Book management in Lync Server 2013</span></span>](lync-server-2013-test-csaddressbookservice-for-address-book-management.md)

  - [<span data-ttu-id="d4b7e-114">Lync Server 2013 中用於通訊錄管理的 Test-CsAddressBookWebQuery</span><span class="sxs-lookup"><span data-stu-id="d4b7e-114">Test-CsAddressBookWebQuery for Address Book management in Lync Server 2013</span></span>](lync-server-2013-test-csaddressbookwebquery-for-address-book-management.md)

  - [<span data-ttu-id="d4b7e-115">Lync Server 2013 中用於通訊錄管理的 Update-CsAddressBook</span><span class="sxs-lookup"><span data-stu-id="d4b7e-115">Update-CsAddressBook for Address Book management in Lync Server 2013</span></span>](lync-server-2013-update-csaddressbook-for-address-book-management.md)

  - [<span data-ttu-id="d4b7e-116">Lync Server 2013 中用於通訊錄管理的 New-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="d4b7e-116">New-CsClientPolicy for Address Book management in Lync Server 2013</span></span>](lync-server-2013-new-csclientpolicy-for-address-book-management.md)

  - [<span data-ttu-id="d4b7e-117">Lync Server 2013 中用於通訊錄管理的 Set-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="d4b7e-117">Set-CsClientPolicy for Address Book management in Lync Server 2013</span></span>](lync-server-2013-set-csclientpolicy-for-address-book-management.md)

  - [<span data-ttu-id="d4b7e-118">Lync Server 2013 中用於通訊錄管理的 Get-CsService</span><span class="sxs-lookup"><span data-stu-id="d4b7e-118">Get-CsService for Address Book management in Lync Server 2013</span></span>](lync-server-2013-get-csservice-for-address-book-management.md)

  - [<span data-ttu-id="d4b7e-119">Lync Server 2013 中用於通訊錄管理的 New-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="d4b7e-119">New-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-New-CsWebServiceConfiguration-for-address-book-management.md)

  - [<span data-ttu-id="d4b7e-120">Lync Server 2013 中用於通訊錄管理的 Get-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="d4b7e-120">Get-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-get-cswebserviceconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="d4b7e-121">Lync Server 2013 中用於通訊錄管理的 Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="d4b7e-121">Set-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-set-cswebserviceconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="d4b7e-122">Lync Server 2013 中用於通訊錄管理的 Remove-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="d4b7e-122">Remove-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-remove-cswebserviceconfiguration-for-address-book-management.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="d4b7e-123">相關章節</span><span class="sxs-lookup"><span data-stu-id="d4b7e-123">Related Sections</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d4b7e-124">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d4b7e-124">See Also</span></span>


[https://go.microsoft.com/fwlink/p/?linkId=205826](https://go.microsoft.com/fwlink/p/?linkid=205826)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


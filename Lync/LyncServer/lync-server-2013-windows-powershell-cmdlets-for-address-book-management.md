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
ms.openlocfilehash: 5ec10f3e3d3d58a790ddc60fd1af1d1b09765685
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727463"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="windows-powershell-cmdlets-for-address-book-services-in-lync-server-2013"></a><span data-ttu-id="032db-102">Lync Server 2013 中的通訊錄服務的 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="032db-102">Windows PowerShell cmdlets for Address Book Services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="032db-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="032db-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="032db-104">Lync Server 提供了許多 Windows PowerShell 命令列介面 Cmdlet 來管理和設定通訊錄服務。</span><span class="sxs-lookup"><span data-stu-id="032db-104">Lync Server provides a number of Windows PowerShell command-line interface cmdlets to manage and configure the Address Book service.</span></span> <span data-ttu-id="032db-105">在舊版 Office 通訊伺服器中使用的 ABServer 命令，會取代其中一些 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="032db-105">Some of these cmdlets are replacements for the ABServer.exe commands used in previous versions of Office Communications Server.</span></span> <span data-ttu-id="032db-106">下列主題是用來設定、建立及取得通訊錄服務之資訊的 Cmdlet，以及在用戶端取得通訊錄服務時，通訊錄服務所使用之 Web 服務的相關資訊。檔案和設定。</span><span class="sxs-lookup"><span data-stu-id="032db-106">In the following topics are the cmdlets that are used to set, create, and retrieve information about the Address Book service, its configuration and information about the Web services that the Address Book service uses when clients retrieve Address Book service files and settings.</span></span>

<span data-ttu-id="032db-107">所有這些 Cmdlet 都是透過在已安裝管理工具之伺服器或工作站上的 Lync server 工具中找到的 Lync Server 管理命令介面進行發佈。</span><span class="sxs-lookup"><span data-stu-id="032db-107">All of these cmdlets are issued through the Lync Server Management Shell found in the Lync Server tools on a server or workstation where the administration tools have been installed.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="032db-108">本節內容</span><span class="sxs-lookup"><span data-stu-id="032db-108">In This Section</span></span>

  - [<span data-ttu-id="032db-109">Lync Server 2013 中的通訊錄管理的新 CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="032db-109">New-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-New-CsAddressBookConfiguration-for-address-book-management.md)

  - [<span data-ttu-id="032db-110">在 Lync Server 2013 中設定通訊錄管理 CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="032db-110">Set-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-set-csaddressbookconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="032db-111">在 Lync Server 2013 中取得通訊錄管理的 CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="032db-111">Get-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-get-csaddressbookconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="032db-112">在 Lync Server 2013 中移除通訊錄管理的 CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="032db-112">Remove-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-remove-csaddressbookconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="032db-113">在 Lync Server 2013 中 CsAddressBookService 通訊錄管理的測試</span><span class="sxs-lookup"><span data-stu-id="032db-113">Test-CsAddressBookService for Address Book management in Lync Server 2013</span></span>](lync-server-2013-test-csaddressbookservice-for-address-book-management.md)

  - [<span data-ttu-id="032db-114">在 Lync Server 2013 中 CsAddressBookWebQuery 通訊錄管理的測試</span><span class="sxs-lookup"><span data-stu-id="032db-114">Test-CsAddressBookWebQuery for Address Book management in Lync Server 2013</span></span>](lync-server-2013-test-csaddressbookwebquery-for-address-book-management.md)

  - [<span data-ttu-id="032db-115">CsAddressBook 在 Lync Server 2013 中的通訊錄管理的更新</span><span class="sxs-lookup"><span data-stu-id="032db-115">Update-CsAddressBook for Address Book management in Lync Server 2013</span></span>](lync-server-2013-update-csaddressbook-for-address-book-management.md)

  - [<span data-ttu-id="032db-116">Lync Server 2013 中的通訊錄管理的新 CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="032db-116">New-CsClientPolicy for Address Book management in Lync Server 2013</span></span>](lync-server-2013-new-csclientpolicy-for-address-book-management.md)

  - [<span data-ttu-id="032db-117">在 Lync Server 2013 中設定通訊錄管理 CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="032db-117">Set-CsClientPolicy for Address Book management in Lync Server 2013</span></span>](lync-server-2013-set-csclientpolicy-for-address-book-management.md)

  - [<span data-ttu-id="032db-118">在 Lync Server 2013 中取得通訊錄管理的 CsService</span><span class="sxs-lookup"><span data-stu-id="032db-118">Get-CsService for Address Book management in Lync Server 2013</span></span>](lync-server-2013-get-csservice-for-address-book-management.md)

  - [<span data-ttu-id="032db-119">Lync Server 2013 中的通訊錄管理的新 CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="032db-119">New-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-New-CsWebServiceConfiguration-for-address-book-management.md)

  - [<span data-ttu-id="032db-120">在 Lync Server 2013 中取得通訊錄管理的 CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="032db-120">Get-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-get-cswebserviceconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="032db-121">在 Lync Server 2013 中設定通訊錄管理 CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="032db-121">Set-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-set-cswebserviceconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="032db-122">在 Lync Server 2013 中移除通訊錄管理的 CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="032db-122">Remove-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-remove-cswebserviceconfiguration-for-address-book-management.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="032db-123">相關各節</span><span class="sxs-lookup"><span data-stu-id="032db-123">Related Sections</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="032db-124">請參閱</span><span class="sxs-lookup"><span data-stu-id="032db-124">See Also</span></span>


[http://go.microsoft.com/fwlink/p/?linkId=205826](http://go.microsoft.com/fwlink/p/?linkid=205826)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


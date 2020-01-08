---
title: Lync Server 2013：準備 Active Directory 結構描述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing the Active Directory schema
ms:assetid: 067726ae-fd3f-4133-a32f-26d2603ac674
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398119(v=OCS.15)
ms:contentKeyID: 48183300
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5479bfbb0774ddd68015de470de082f0cc185b98
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976834"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-active-directory-schema-in-lync-server-2013"></a><span data-ttu-id="35751-102">在 Lync Server 2013 中準備 Active Directory 結構描述</span><span class="sxs-lookup"><span data-stu-id="35751-102">Preparing the Active Directory schema in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35751-103">_**主題上次修改日期：** 2012-08-27_</span><span class="sxs-lookup"><span data-stu-id="35751-103">_**Topic Last Modified:** 2012-08-27_</span></span>

<span data-ttu-id="35751-104">在您開始準備 Active Directory 網域服務之前，您可以使用文字編輯器（例如 Windows Notepad）來開啟架構檔案，或參閱 Lync Server 2013 用來檢查將針對 Lync Server 2013 進行修改之所有 Active Directory 網域服務架構擴充的[Active directory 架構副檔名、類別及屬性](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)。</span><span class="sxs-lookup"><span data-stu-id="35751-104">Before you begin preparing Active Directory Domain Services, you can open the schema files by using a text editor, such as Windows Notepad, or see [Active Directory schema extensions, classes, and attributes used by Lync Server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md) to review all the Active Directory Domain Services schema extensions that will be modified for Lync Server 2013.</span></span> <span data-ttu-id="35751-105">Lync Server 使用四個架構檔：</span><span class="sxs-lookup"><span data-stu-id="35751-105">Lync Server uses four schema files:</span></span>

  - <span data-ttu-id="35751-106">ExternalSchema，用於與 Microsoft Exchange Server 的互通性</span><span class="sxs-lookup"><span data-stu-id="35751-106">ExternalSchema.ldf, which is used for interoperability with Microsoft Exchange Server</span></span>

  - <span data-ttu-id="35751-107">ServerSchema，這是主要的 Lync Server 2013 架構檔</span><span class="sxs-lookup"><span data-stu-id="35751-107">ServerSchema.ldf, which is the primary Lync Server 2013 schema file</span></span>

  - <span data-ttu-id="35751-108">BackCompatSchema，可用於與先前版本中的任何元件進行互通性</span><span class="sxs-lookup"><span data-stu-id="35751-108">BackCompatSchema.ldf, which is used for interoperability with any components from prior releases</span></span>

  - <span data-ttu-id="35751-109">VersionSchema，用於預準備架構的版本資訊</span><span class="sxs-lookup"><span data-stu-id="35751-109">VersionSchema.ldf, which is used for version information of the prepared schema</span></span>

<span data-ttu-id="35751-110">所有的 .ldf 檔案都會在架構準備期間進行安裝，不論您是從先前的版本進行遷移，還是執行全新安裝。</span><span class="sxs-lookup"><span data-stu-id="35751-110">All .ldf files are installed during schema preparation, regardless of whether you are migrating from a previous release or performing a clean installation.</span></span> <span data-ttu-id="35751-111">這些架構檔案是按照前面清單中顯示的順序來安裝，並位於安裝媒體\\上\\的 [支援架構] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="35751-111">These schema files are installed in the sequence shown in the preceding list and are located in the \\Support\\schema folder on the installation media.</span></span>

<span data-ttu-id="35751-112">Lync Server 架構擴充功能會在所有網域中複製，這會影響網路流量。</span><span class="sxs-lookup"><span data-stu-id="35751-112">The Lync Server schema extensions are replicated across all domains, which impacts network traffic.</span></span> <span data-ttu-id="35751-113">當網路使用量較低時，請一次執行架構準備。</span><span class="sxs-lookup"><span data-stu-id="35751-113">Run schema preparation at a time when network usage is low.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="35751-114">如果您需要新增 Microsoft® Office Communicator Mobile 2007 R2 for JAVA 及 Microsoft® Office Communicator Mobile for Nokia 1.0 行動用戶端至 Lync Server 2013 部署，您必須準備 Microsoft Office 的 Active Directory 架構在安裝 Lync Server 2013 期間，通訊伺服器 2007 R2。</span><span class="sxs-lookup"><span data-stu-id="35751-114">If you need to add support for Microsoft® Office Communicator Mobile 2007 R2 for Java and Microsoft® Office Communicator Mobile for Nokia 1.0 mobile clients to your Lync Server 2013 deployment, you need to prepare the Active Directory schema for Microsoft Office Communications Server 2007 R2 during installation of Lync Server 2013.</span></span> <span data-ttu-id="35751-115">如需軟體和檔，請參閱<A href="http://go.microsoft.com/fwlink/p/?linkid=207172">http://go.microsoft.com/fwlink/p/?linkId=207172</A>。</span><span class="sxs-lookup"><span data-stu-id="35751-115">For the necessary software and documentation, see <A href="http://go.microsoft.com/fwlink/p/?linkid=207172">http://go.microsoft.com/fwlink/p/?linkId=207172</A>.</span></span>



</div>

<div>

## <a name="adsi-edit"></a><span data-ttu-id="35751-116">ADSI 編輯</span><span class="sxs-lookup"><span data-stu-id="35751-116">ADSI Edit</span></span>

<span data-ttu-id="35751-117">Active Directory 服務介面編輯器（ADSI 編輯）是一個 AD DS 管理工具，可讓您用來驗證架構準備及複製。</span><span class="sxs-lookup"><span data-stu-id="35751-117">Active Directory Service Interfaces Editor (ADSI Edit) is an AD DS administration tool that you can use to verify schema preparation and replication.</span></span>

<span data-ttu-id="35751-118">當您安裝 AD DS 角色以使伺服器成為網網域控制站時，預設會安裝 ADSI 編輯。</span><span class="sxs-lookup"><span data-stu-id="35751-118">ADSI Edit is installed by default when you install the AD DS role to make a server a domain controller.</span></span> <span data-ttu-id="35751-119">針對 Windows Server 2008 和 Windows Server 2008 R2，ADSI 編輯（adsiedit）包含在遠端伺服器管理工具（RSAT）中。</span><span class="sxs-lookup"><span data-stu-id="35751-119">For Windows Server 2008 and Windows Server 2008 R2, ADSI Edit (adsiedit.msc) is included with the Remote Server Administration Tools (RSAT).</span></span> <span data-ttu-id="35751-120">您也可以在網域成員伺服器或獨立伺服器上安裝 RSAT。</span><span class="sxs-lookup"><span data-stu-id="35751-120">You can also install RSAT on domain member servers or stand-alone servers.</span></span> <span data-ttu-id="35751-121">預設會在您安裝 Windows 時將 RSAT 套件複製到這些伺服器，但預設不會安裝。</span><span class="sxs-lookup"><span data-stu-id="35751-121">The RSAT package is copied to these servers by default when you install Windows, but it is not installed by default.</span></span> <span data-ttu-id="35751-122">您可以使用伺服器管理員安裝個別的工具。</span><span class="sxs-lookup"><span data-stu-id="35751-122">You install individual tools by using Server Manager.</span></span> <span data-ttu-id="35751-123">ADSI 編輯包含在**角色管理工具**、 **Active Directory 網域服務工具**、 **active directory 網網域控制站工具**底下。</span><span class="sxs-lookup"><span data-stu-id="35751-123">ADSI Edit is included under **Role Administration Tools**, **Active Directory Domain Services Tools**, **Active Directory Domain Controller Tools**.</span></span>

<span data-ttu-id="35751-124">針對 Windows Server 2003，[支援工具] 附帶 ADSI [編輯]。</span><span class="sxs-lookup"><span data-stu-id="35751-124">For Windows Server 2003, ADSI Edit is included with the Support Tools.</span></span> <span data-ttu-id="35751-125">支援工具可從 [ \\支援\\工具] 資料夾中的 windows server 2003 光碟取得，您也可以從 [Windows server 2003 Service Pack 2 32-位支援工具] 下載。 [http://go.microsoft.com/fwlink/p/?linkId=125770](http://go.microsoft.com/fwlink/p/?linkid=125770)</span><span class="sxs-lookup"><span data-stu-id="35751-125">The Support Tools are available from the Windows Server 2003 CD in the \\SUPPORT\\TOOLS folder, or you can download them from “Windows Server 2003 Service Pack 2 32-bit Support Tools” at [http://go.microsoft.com/fwlink/p/?linkId=125770](http://go.microsoft.com/fwlink/p/?linkid=125770).</span></span> <span data-ttu-id="35751-126">您可以從「安裝 Windows 支援工具」中取得從產品光碟安裝支援工具的指示[http://go.microsoft.com/fwlink/p/?linkId=125771](http://go.microsoft.com/fwlink/p/?linkid=125771)。</span><span class="sxs-lookup"><span data-stu-id="35751-126">Instructions for installing the Support Tools from the product CD are available from “Install Windows Support Tools” at [http://go.microsoft.com/fwlink/p/?linkId=125771](http://go.microsoft.com/fwlink/p/?linkid=125771).</span></span> <span data-ttu-id="35751-127">當您安裝支援工具時，會自動註冊 Adsiedit .dll。</span><span class="sxs-lookup"><span data-stu-id="35751-127">Adsiedit.dll is automatically registered when you install the support tools.</span></span> <span data-ttu-id="35751-128">不過，如果您已將檔案複製到您的電腦，您必須先執行**regsvr32**命令來註冊 adsiedit .dll 檔案，然後才能執行此工具。</span><span class="sxs-lookup"><span data-stu-id="35751-128">If, however, you copied the files to your computer, you must run the **regsvr32** command to register the adsiedit.dll file before you can run the tool.</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="35751-129">本節內容</span><span class="sxs-lookup"><span data-stu-id="35751-129">In This Section</span></span>

  - [<span data-ttu-id="35751-130">在 Lync Server 2013 中執行 Active Directory 架構準備</span><span class="sxs-lookup"><span data-stu-id="35751-130">Running Active Directory schema preparation in Lync Server 2013</span></span>](lync-server-2013-running-schema-preparation.md)

  - [<span data-ttu-id="35751-131">在 Lync Server 2013 中驗證 Active Directory 結構描述複寫</span><span class="sxs-lookup"><span data-stu-id="35751-131">Verifying Active Directory schema replication in Lync Server 2013</span></span>](lync-server-2013-verifying-schema-replication.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="35751-132">請參閱</span><span class="sxs-lookup"><span data-stu-id="35751-132">See Also</span></span>


[<span data-ttu-id="35751-133">為 Lync Server 2013 準備樹系</span><span class="sxs-lookup"><span data-stu-id="35751-133">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
[<span data-ttu-id="35751-134">針對 Lync Server 2013 準備網域</span><span class="sxs-lookup"><span data-stu-id="35751-134">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


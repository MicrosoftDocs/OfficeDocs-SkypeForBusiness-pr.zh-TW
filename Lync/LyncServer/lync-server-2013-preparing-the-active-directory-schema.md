---
title: Lync Server 2013：準備 Active Directory 架構
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the Active Directory schema
ms:assetid: 067726ae-fd3f-4133-a32f-26d2603ac674
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398119(v=OCS.15)
ms:contentKeyID: 48183300
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efabd082fce4dba5cf210e2c0f9c390324474cd2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201779"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-the-active-directory-schema-in-lync-server-2013"></a><span data-ttu-id="67eac-102">在 Lync Server 2013 中準備 Active Directory 架構</span><span class="sxs-lookup"><span data-stu-id="67eac-102">Preparing the Active Directory schema in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67eac-103">_**主題上次修改日期：** 2012-08-27_</span><span class="sxs-lookup"><span data-stu-id="67eac-103">_**Topic Last Modified:** 2012-08-27_</span></span>

<span data-ttu-id="67eac-104">在您開始準備 Active Directory 網域服務之前，您可以使用文字編輯器（例如 Windows Notepad）來開啟架構檔案，或查看[Lync server 2013 所使用的 Active directory 架構副檔名、類別和屬性](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)，以查看將針對 Lync server 2013 修改的所有 Active Directory 網域服務架構擴充。</span><span class="sxs-lookup"><span data-stu-id="67eac-104">Before you begin preparing Active Directory Domain Services, you can open the schema files by using a text editor, such as Windows Notepad, or see [Active Directory schema extensions, classes, and attributes used by Lync Server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md) to review all the Active Directory Domain Services schema extensions that will be modified for Lync Server 2013.</span></span> <span data-ttu-id="67eac-105">Lync Server 使用四個架構檔案：</span><span class="sxs-lookup"><span data-stu-id="67eac-105">Lync Server uses four schema files:</span></span>

  - <span data-ttu-id="67eac-106">用於與 Microsoft Exchange Server 進行互通性的 ExternalSchema.ldf</span><span class="sxs-lookup"><span data-stu-id="67eac-106">ExternalSchema.ldf, which is used for interoperability with Microsoft Exchange Server</span></span>

  - <span data-ttu-id="67eac-107">ServerSchema.ldf，也就是主要 Lync Server 2013 架構檔案</span><span class="sxs-lookup"><span data-stu-id="67eac-107">ServerSchema.ldf, which is the primary Lync Server 2013 schema file</span></span>

  - <span data-ttu-id="67eac-108">BackCompatSchema.ldf，這個檔案用於提供與任何舊版元件的互通性</span><span class="sxs-lookup"><span data-stu-id="67eac-108">BackCompatSchema.ldf, which is used for interoperability with any components from prior releases</span></span>

  - <span data-ttu-id="67eac-109">VersionSchema.ldf，這個檔案用於提供預備架構的版本資訊</span><span class="sxs-lookup"><span data-stu-id="67eac-109">VersionSchema.ldf, which is used for version information of the prepared schema</span></span>

<span data-ttu-id="67eac-110">不論您是從舊版進行移轉或執行全新安裝，所有 .ldf 檔案都是在架構準備期間進行安裝。</span><span class="sxs-lookup"><span data-stu-id="67eac-110">All .ldf files are installed during schema preparation, regardless of whether you are migrating from a previous release or performing a clean installation.</span></span> <span data-ttu-id="67eac-111">這些架構檔案會依上述清單中顯示的順序安裝，並位於 \\ \\ 安裝媒體上的 [支援架構] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="67eac-111">These schema files are installed in the sequence shown in the preceding list and are located in the \\Support\\schema folder on the installation media.</span></span>

<span data-ttu-id="67eac-112">Lync Server 架構擴充會在所有網域間進行複製，這會影響網路流量。</span><span class="sxs-lookup"><span data-stu-id="67eac-112">The Lync Server schema extensions are replicated across all domains, which impacts network traffic.</span></span> <span data-ttu-id="67eac-113">請在網路使用率較低時執行架構準備作業。</span><span class="sxs-lookup"><span data-stu-id="67eac-113">Run schema preparation at a time when network usage is low.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="67eac-114">如果您需要將 Microsoft® Office Communicator Mobile 2007 R2 for JAVA 和 Microsoft® Office Communicator mobile for Nokia 1.0 行動用戶端新增至您的 Lync Server 2013 部署，您必須在安裝 Lync Server 2013 期間，準備好 Microsoft Office 通訊2007伺服器的 Active Directory 架構。</span><span class="sxs-lookup"><span data-stu-id="67eac-114">If you need to add support for Microsoft® Office Communicator Mobile 2007 R2 for Java and Microsoft® Office Communicator Mobile for Nokia 1.0 mobile clients to your Lync Server 2013 deployment, you need to prepare the Active Directory schema for Microsoft Office Communications Server 2007 R2 during installation of Lync Server 2013.</span></span> <span data-ttu-id="67eac-115">如需必要的軟體及檔，請參閱 <A href="https://go.microsoft.com/fwlink/p/?linkid=207172">https://go.microsoft.com/fwlink/p/?linkId=207172</A> 。</span><span class="sxs-lookup"><span data-stu-id="67eac-115">For the necessary software and documentation, see <A href="https://go.microsoft.com/fwlink/p/?linkid=207172">https://go.microsoft.com/fwlink/p/?linkId=207172</A>.</span></span>



</div>

<div>

## <a name="adsi-edit"></a><span data-ttu-id="67eac-116">ADSI 編輯器</span><span class="sxs-lookup"><span data-stu-id="67eac-116">ADSI Edit</span></span>

<span data-ttu-id="67eac-117">Active Directory 服務介面編輯器 (ADSI 編輯器) 是您可以用於驗證架構準備和複寫的 AD DS 系統管理工具。</span><span class="sxs-lookup"><span data-stu-id="67eac-117">Active Directory Service Interfaces Editor (ADSI Edit) is an AD DS administration tool that you can use to verify schema preparation and replication.</span></span>

<span data-ttu-id="67eac-118">當您安裝 AD DS 角色以使伺服器成為網域控制站時，預設會安裝 ADSI 編輯器。</span><span class="sxs-lookup"><span data-stu-id="67eac-118">ADSI Edit is installed by default when you install the AD DS role to make a server a domain controller.</span></span> <span data-ttu-id="67eac-119">若為 Windows Server 2008 和 Windows Server 2008 R2，ADSI Edit (adsi) 隨附 (RSAT) 的遠端伺服器管理工具。</span><span class="sxs-lookup"><span data-stu-id="67eac-119">For Windows Server 2008 and Windows Server 2008 R2, ADSI Edit (adsiedit.msc) is included with the Remote Server Administration Tools (RSAT).</span></span> <span data-ttu-id="67eac-120">您也可以在網域成員伺服器或獨立伺服器上安裝 RSAT。</span><span class="sxs-lookup"><span data-stu-id="67eac-120">You can also install RSAT on domain member servers or stand-alone servers.</span></span> <span data-ttu-id="67eac-121">RSAT 套件預設會在您安裝 Windows 時複製到這些伺服器，但並不會進行安裝。</span><span class="sxs-lookup"><span data-stu-id="67eac-121">The RSAT package is copied to these servers by default when you install Windows, but it is not installed by default.</span></span> <span data-ttu-id="67eac-122">您可以使用伺服器管理員來安裝個別的工具。</span><span class="sxs-lookup"><span data-stu-id="67eac-122">You install individual tools by using Server Manager.</span></span> <span data-ttu-id="67eac-123">「ADSI 編輯器」包含在 **[角色管理工具]**、**[Active Directory 網域服務工具]**、**[Active Directory 網域控制站工具]** 之下。</span><span class="sxs-lookup"><span data-stu-id="67eac-123">ADSI Edit is included under **Role Administration Tools**, **Active Directory Domain Services Tools**, **Active Directory Domain Controller Tools**.</span></span>

<span data-ttu-id="67eac-124">如果是 Windows Server 2003，ADSI 編輯器包含在支援工具中。</span><span class="sxs-lookup"><span data-stu-id="67eac-124">For Windows Server 2003, ADSI Edit is included with the Support Tools.</span></span> <span data-ttu-id="67eac-125">支援工具可在 [支援工具] 資料夾中的 [Windows Server 2003 CD] 中取得 \\ \\ ，您也可以從「windows Server 2003 Service Pack 2 32-位支援工具」下載這些工具 [https://go.microsoft.com/fwlink/p/?linkId=125770](https://go.microsoft.com/fwlink/p/?linkid=125770) 。</span><span class="sxs-lookup"><span data-stu-id="67eac-125">The Support Tools are available from the Windows Server 2003 CD in the \\SUPPORT\\TOOLS folder, or you can download them from “Windows Server 2003 Service Pack 2 32-bit Support Tools” at [https://go.microsoft.com/fwlink/p/?linkId=125770](https://go.microsoft.com/fwlink/p/?linkid=125770).</span></span> <span data-ttu-id="67eac-126">您可以從「安裝 Windows 支援工具」中取得安裝產品 CD 支援工具的指示 [https://go.microsoft.com/fwlink/p/?linkId=125771](https://go.microsoft.com/fwlink/p/?linkid=125771) 。</span><span class="sxs-lookup"><span data-stu-id="67eac-126">Instructions for installing the Support Tools from the product CD are available from “Install Windows Support Tools” at [https://go.microsoft.com/fwlink/p/?linkId=125771](https://go.microsoft.com/fwlink/p/?linkid=125771).</span></span> <span data-ttu-id="67eac-127">當您安裝支援工具時，就會自動登錄 Adsiedit.dll。</span><span class="sxs-lookup"><span data-stu-id="67eac-127">Adsiedit.dll is automatically registered when you install the support tools.</span></span> <span data-ttu-id="67eac-128">不過，若您將檔案複製到電腦，則必須先執行 **regsvr32** 命令來登錄 adsiedit.dll 檔案，才能執行該工具。</span><span class="sxs-lookup"><span data-stu-id="67eac-128">If, however, you copied the files to your computer, you must run the **regsvr32** command to register the adsiedit.dll file before you can run the tool.</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="67eac-129">本章節內容</span><span class="sxs-lookup"><span data-stu-id="67eac-129">In This Section</span></span>

  - [<span data-ttu-id="67eac-130">在 Lync Server 2013 中執行 Active Directory 架構準備</span><span class="sxs-lookup"><span data-stu-id="67eac-130">Running Active Directory schema preparation in Lync Server 2013</span></span>](lync-server-2013-running-schema-preparation.md)

  - [<span data-ttu-id="67eac-131">在 Lync Server 2013 中驗證 Active Directory 架構複寫</span><span class="sxs-lookup"><span data-stu-id="67eac-131">Verifying Active Directory schema replication in Lync Server 2013</span></span>](lync-server-2013-verifying-schema-replication.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="67eac-132">另請參閱</span><span class="sxs-lookup"><span data-stu-id="67eac-132">See Also</span></span>


[<span data-ttu-id="67eac-133">準備 Lync Server 2013 的樹系</span><span class="sxs-lookup"><span data-stu-id="67eac-133">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
[<span data-ttu-id="67eac-134">準備 Lync Server 2013 的網域</span><span class="sxs-lookup"><span data-stu-id="67eac-134">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


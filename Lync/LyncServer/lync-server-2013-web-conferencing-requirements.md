---
title: Lync Server 2013：網路會議需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Web conferencing requirements
ms:assetid: 125f847c-58ab-450f-ae43-41219fd38477
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619171(v=OCS.15)
ms:contentKeyID: 49733559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 186f597c4328c8cee5085e7e599228b60c300a96
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758513"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="web-conferencing-requirements-in-lync-server-2013"></a><span data-ttu-id="b27f5-102">Lync Server 2013 的網路會議需求</span><span class="sxs-lookup"><span data-stu-id="b27f5-102">Web conferencing requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b27f5-103">_**主題上次修改日期：** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="b27f5-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="b27f5-104">如果您已選擇啟用 [web 會議]，您必須規劃下列各項：</span><span class="sxs-lookup"><span data-stu-id="b27f5-104">If you have chosen to enable web conferencing, you need to plan for the following:</span></span>

  - <span></span>  
    <span data-ttu-id="b27f5-105">存取儲存網路會議內容所用的檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="b27f5-105">Access to the file store, which is used for storing web conferencing content.</span></span>

  - <span></span>  
    <span data-ttu-id="b27f5-106">與 Office Web Apps Server 整合，這是為了在會議期間共用 PowerPoint 檔案所需要的。</span><span class="sxs-lookup"><span data-stu-id="b27f5-106">Integration with Office Web Apps Server, which is necessary in order to share PowerPoint files during a conference.</span></span>

<div>

## <a name="file-store"></a><span data-ttu-id="b27f5-107">檔案存放區</span><span class="sxs-lookup"><span data-stu-id="b27f5-107">File Store</span></span>

<span data-ttu-id="b27f5-108">Lync Server 2013 網路會議服務會儲存在檔存放區中的會議期間共用的內容。</span><span class="sxs-lookup"><span data-stu-id="b27f5-108">The Lync Server 2013 web conferencing service stores content shared during meetings in the file store.</span></span> <span data-ttu-id="b27f5-109">在部署過程中，您必須指定要用來做為標準版 server 或 Enterprise Edition 前端池之檔案存放區的檔案共用。</span><span class="sxs-lookup"><span data-stu-id="b27f5-109">As part of deployment, you must specify a file share to be used as the file store for the either Standard Edition server or Enterprise Edition Front End pool.</span></span> <span data-ttu-id="b27f5-110">您可以將現有的檔案共用用於檔案存放區，或者您可以指定新的檔案共用，方法是指定檔案共用所在的檔案伺服器的完整功能變數名稱（FQDN），以及新檔案共用的資料夾名稱。</span><span class="sxs-lookup"><span data-stu-id="b27f5-110">You can use an existing file share for the file store or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span><span data-ttu-id="b27f5-111">如需詳細資訊，請參閱拓撲產生器-定義前端的檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="b27f5-111">  For more information, see Topology Builder – Define the File Store for the Front End.</span></span> <span data-ttu-id="b27f5-112">網路會議服務會先加密內容，然後再將內容儲存在檔案存放區中。</span><span class="sxs-lookup"><span data-stu-id="b27f5-112">The web conferencing service encrypts the content before it stores the content in the file store.</span></span>

<span data-ttu-id="b27f5-113">Lync Server 2013 支援在直連儲存空間（DAS）或儲存區域網路（SAN）上使用檔案共用，包括分散式檔案系統（DFS），以及檔案存放區的獨立磁碟容錯陣列（RAID）。</span><span class="sxs-lookup"><span data-stu-id="b27f5-113">Lync Server 2013 supports using file shares on either direct attached storage (DAS) or a storage area network (SAN), including Distributed File System (DFS) and on a redundant array of independent disks (RAID) for file stores.</span></span> <span data-ttu-id="b27f5-114">在 Lync Server 部署嚮導定義檔案共用的位置之後，Lync Server 會在檔案共用中建立一個類似以下內容的資料夾結構：</span><span class="sxs-lookup"><span data-stu-id="b27f5-114">After the Lync Server Deployment Wizard has defined the location of the file share, Lync Server creates a folder structure within the file share similar to:</span></span>

  - <span data-ttu-id="b27f5-115">1-ApplicationServer-1</span><span class="sxs-lookup"><span data-stu-id="b27f5-115">1-ApplicationServer-1</span></span>

  - <span data-ttu-id="b27f5-116">1-CentralMgmt-1</span><span class="sxs-lookup"><span data-stu-id="b27f5-116">1-CentralMgmt-1</span></span>

  - <span data-ttu-id="b27f5-117">1-WebServices-1</span><span class="sxs-lookup"><span data-stu-id="b27f5-117">1-WebServices-1</span></span>
    
      - <span data-ttu-id="b27f5-118">CollabContent</span><span class="sxs-lookup"><span data-stu-id="b27f5-118">CollabContent</span></span>
    
      - <span data-ttu-id="b27f5-119">CollabMetadata</span><span class="sxs-lookup"><span data-stu-id="b27f5-119">CollabMetadata</span></span>
    
      - <span data-ttu-id="b27f5-120">DataConf</span><span class="sxs-lookup"><span data-stu-id="b27f5-120">DataConf</span></span>

<span data-ttu-id="b27f5-121">然後，web 會議服務會在 [WebServices] 資料夾中的 [CollabContent] 和 [CollabMetadata] 資料夾中儲存 PowerPoint 投影片、白板、投票及附件等內容。</span><span class="sxs-lookup"><span data-stu-id="b27f5-121">The web conferencing service then stores content such as PowerPoint slides, whiteboards, polls, and attachments in the CollabContent and CollabMetadata folders, located in the WebServices folder.</span></span>

<span data-ttu-id="b27f5-122">系統管理員必須在檔案共用上設定許可權，才能讓 RTC 群組擁有必要的讀取和寫入存取權。</span><span class="sxs-lookup"><span data-stu-id="b27f5-122">The administrator must set permissions on the file share so that RTC groups have the necessary read and write access.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="b27f5-123">如果許可權有任何錯誤，請開啟 [拓撲建立器]，下載並重新發佈現有的拓撲。</span><span class="sxs-lookup"><span data-stu-id="b27f5-123">If you encounter any errors with the permissions, open Topology Builder, download and republish the existing topology.</span></span> <span data-ttu-id="b27f5-124">發佈拓撲將會驗證檔案共用許可權，並視需要重設檔案。</span><span class="sxs-lookup"><span data-stu-id="b27f5-124">Publishing the topology will verify the file share permissions and reset them if needed.</span></span>



</div>

<span data-ttu-id="b27f5-125">您可以使用下列設定來管理會議內容的儲存方式：</span><span class="sxs-lookup"><span data-stu-id="b27f5-125">You can use the following settings to manage how content is stored for a meeting:</span></span>

  - <span data-ttu-id="b27f5-126">**ContentGracePeriod**（位於[CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration)中）會設定在會議結束後，網路會議內容將在伺服器上保留多長時間。</span><span class="sxs-lookup"><span data-stu-id="b27f5-126">**ContentGracePeriod**, located in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), sets how long web conferencing content will remain on the server after the meeting has ended.</span></span>

  - <span data-ttu-id="b27f5-127">**MaxContentStorageMb**（位於[CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration)中）會設定在單一會議期間儲存內容所允許的最大檔空間量。</span><span class="sxs-lookup"><span data-stu-id="b27f5-127">**MaxContentStorageMb**, located in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), sets the maximum amount of file space allowed for the storage of content during a single meeting.</span></span>

<span data-ttu-id="b27f5-128">**MaxUploadFileSizeMb**不會限制 Lync Web App 的 [檔案上傳] 設定。</span><span class="sxs-lookup"><span data-stu-id="b27f5-128">**MaxUploadFileSizeMb** does not limit the file upload setting for Lync Web App.</span></span> <span data-ttu-id="b27f5-129">Lync Web App 的檔案大小上傳限制是設定為 [大約 30MB]，且由 IIS web.config 檔案所控制：/DataCollabWeb/Int\[Ext\]/Handler/web.config。若要設定 Lync Web App 的檔案大小上傳限制， `maxRequestLength`請`maxAllowedContentLength`更新並放在 web.config 檔案中，如下所示。</span><span class="sxs-lookup"><span data-stu-id="b27f5-129">The file size upload limit for Lync Web App is set to approximately 30MB and is controlled by the IIS web.config file: /DataCollabWeb/Int\[Ext\]/Handler/web.config. To configure the file size upload limit for Lync Web App, update `maxRequestLength` and `maxAllowedContentLength` in the web.config file as shown below.</span></span>

    <system.web>
        <!-- 
            Since this handler is used to upload files to DMCU the request size (in kilobytes) 
            has to fit max allowed file size uploaded by Lync Web App client.
            The timeout has to reflect the min client bandwidth. Timeout of 600 secs 
            and 512 Kbits of *client* bandwidth would result into aproximately 30 Mbytes 
            for Lync Web App upload size limit.
        -->
          <httpRuntime maxRequestLength="500000" executionTimeout="600" />
    
    
    
                    <security>
                    <requestFiltering>
                               <requestLimits maxAllowedContentLength="524288000" />
                    </requestFiltering>
                    </security>

<span data-ttu-id="b27f5-130">您必須為每個前端伺服器更新 web.config 檔案。</span><span class="sxs-lookup"><span data-stu-id="b27f5-130">You must update the web.config file for each Front End Server.</span></span>

</div>

<div>

## <a name="office-web-apps-server"></a><span data-ttu-id="b27f5-131">Office Web Apps 伺服器</span><span class="sxs-lookup"><span data-stu-id="b27f5-131">Office Web Apps Server</span></span>

<span data-ttu-id="b27f5-132">若要使用這些新功能，系統管理員必須安裝 Office Web Apps 伺服器，而且必須設定 Lync Server 2013 與 Office Web Apps 伺服器進行通訊。</span><span class="sxs-lookup"><span data-stu-id="b27f5-132">In order to use these new capabilities administrators must install Office Web Apps Server and they must configure Lync Server 2013 to communicate with Office Web Apps Server.</span></span> <span data-ttu-id="b27f5-133">本檔提供如何設定 Lync Server 2013 以搭配 Office Web Apps 伺服器使用的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="b27f5-133">This documentation provides information on how to configure Lync Server 2013 to work with Office Web Apps Server.</span></span> <span data-ttu-id="b27f5-134">本檔不提供的內容是關於如何安裝 Office Web Apps Server 的資訊。</span><span class="sxs-lookup"><span data-stu-id="b27f5-134">What this documentation does not provide is information about how to install Office Web Apps Server.</span></span> <span data-ttu-id="b27f5-135">如需安裝的詳細資訊，請參閱 Microsoft Office Web Apps <http://go.microsoft.com/fwlink/p/?linkid=257525>部署網站。</span><span class="sxs-lookup"><span data-stu-id="b27f5-135">For installation details, see the Microsoft Office Web Apps Deployment website at <http://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span> <span data-ttu-id="b27f5-136">該指南包括完整的 Office Web Apps 伺服器必備資訊。</span><span class="sxs-lookup"><span data-stu-id="b27f5-136">That guide includes complete prerequisite information for Office Web Apps Server.</span></span> <span data-ttu-id="b27f5-137">請注意，Office Web Apps 伺服器應該安裝在未執行 Lync Server、SQL Server 或任何其他伺服器應用程式的獨立電腦上。</span><span class="sxs-lookup"><span data-stu-id="b27f5-137">Note that Office Web Apps Server should be installed on a stand-alone computer that is not running Lync Server, SQL Server, or any other server application.</span></span> <span data-ttu-id="b27f5-138">（您不得在該電腦上安裝任何版本的 Office）。任何用來執行 Office Web Apps Server 的電腦也必須安裝一組特定的軟體（包括 .NET Framework 4.5 和 Windows PowerShell 3.0）。</span><span class="sxs-lookup"><span data-stu-id="b27f5-138">(You must not have any version of Office installed on that computer.) Any computer used to run Office Web Apps Server must also have a specific set of software installed (including .NET Framework 4.5 and Windows PowerShell 3.0).</span></span> <span data-ttu-id="b27f5-139">Microsoft Office Web Apps 部署網站中提供了這些需求，以及有關設定證書和網際網路資訊服務（IIS）的相關資訊<http://go.microsoft.com/fwlink/p/?linkid=257525>。</span><span class="sxs-lookup"><span data-stu-id="b27f5-139">These requirements, along with information about configuring certificates and Internet Information Services (IIS), are discussed in detail in the Microsoft Office Web Apps Deployment website at <http://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b27f5-140">請參閱</span><span class="sxs-lookup"><span data-stu-id="b27f5-140">See Also</span></span>


[<span data-ttu-id="b27f5-141">Lync Server 2013 中的 web 會議概述</span><span class="sxs-lookup"><span data-stu-id="b27f5-141">Overview of web conferencing in Lync Server 2013</span></span>](lync-server-2013-web-conferencing-overview.md)  
[<span data-ttu-id="b27f5-142">Lync Server 2013 的網路會議部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="b27f5-142">Deployment checklist for web conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-web-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


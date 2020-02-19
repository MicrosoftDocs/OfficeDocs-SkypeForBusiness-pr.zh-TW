---
title: 'Lync Server 2013: Web 會議需求'
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
ms.openlocfilehash: b75663f1e5bc51136ac0a2254944541716ad6f74
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134139"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="web-conferencing-requirements-in-lync-server-2013"></a><span data-ttu-id="419c1-102">Lync Server 2013 中的 web 會議需求</span><span class="sxs-lookup"><span data-stu-id="419c1-102">Web conferencing requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="419c1-103">_**上次修改主題：** 2013年-01-30_</span><span class="sxs-lookup"><span data-stu-id="419c1-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="419c1-104">如果您已選擇要啟用 Web 會議，則需規劃下列事項：</span><span class="sxs-lookup"><span data-stu-id="419c1-104">If you have chosen to enable web conferencing, you need to plan for the following:</span></span>

  - <span></span>  
    <span data-ttu-id="419c1-105">存取檔案存放區，以用來儲存 Web 會議內容。</span><span class="sxs-lookup"><span data-stu-id="419c1-105">Access to the file store, which is used for storing web conferencing content.</span></span>

  - <span></span>  
    <span data-ttu-id="419c1-106">與 Office Web Apps Server，也就是在會議期間共用 PowerPoint 檔案所需的整合。</span><span class="sxs-lookup"><span data-stu-id="419c1-106">Integration with Office Web Apps Server, which is necessary in order to share PowerPoint files during a conference.</span></span>

<div>

## <a name="file-store"></a><span data-ttu-id="419c1-107">檔案存放區</span><span class="sxs-lookup"><span data-stu-id="419c1-107">File Store</span></span>

<span data-ttu-id="419c1-108">Lync Server 2013 web 會議服務儲存的檔案存放區中的會議期間共用的內容。</span><span class="sxs-lookup"><span data-stu-id="419c1-108">The Lync Server 2013 web conferencing service stores content shared during meetings in the file store.</span></span> <span data-ttu-id="419c1-109">部署的一部分，您必須指定檔案共用，以做為檔案存放區的 [Standard Edition server 或 Enterprise Edition 前端集區。</span><span class="sxs-lookup"><span data-stu-id="419c1-109">As part of deployment, you must specify a file share to be used as the file store for the either Standard Edition server or Enterprise Edition Front End pool.</span></span> <span data-ttu-id="419c1-110">您可以使用現有的檔案共用的檔案存放區，或您可以指定新的檔案共用，藉由指定所在的檔案共用，就是位於檔案伺服器的完整的網域名稱 (FQDN) 和新的檔案共用的資料夾名稱。</span><span class="sxs-lookup"><span data-stu-id="419c1-110">You can use an existing file share for the file store or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span><span data-ttu-id="419c1-111">如需詳細資訊，請參閱定義前端的檔案存放區拓撲產生器 –。</span><span class="sxs-lookup"><span data-stu-id="419c1-111">  For more information, see Topology Builder – Define the File Store for the Front End.</span></span> <span data-ttu-id="419c1-112">Web 會議服務加密內容之前它的檔案存放區中儲存的內容。</span><span class="sxs-lookup"><span data-stu-id="419c1-112">The web conferencing service encrypts the content before it stores the content in the file store.</span></span>

<span data-ttu-id="419c1-113">Lync Server 2013 支援在直接附加儲存裝置 (DAS) 或儲存區域網路 (SAN)，包括分散式檔案系統 (DFS) 和備援獨立磁碟陣列 (RAID) 上使用檔案共用的檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="419c1-113">Lync Server 2013 supports using file shares on either direct attached storage (DAS) or a storage area network (SAN), including Distributed File System (DFS) and on a redundant array of independent disks (RAID) for file stores.</span></span> <span data-ttu-id="419c1-114">Lync Server 部署精靈已定義的檔案共用位置之後，Lync Server 會建立內的檔案共用資料夾結構如下：</span><span class="sxs-lookup"><span data-stu-id="419c1-114">After the Lync Server Deployment Wizard has defined the location of the file share, Lync Server creates a folder structure within the file share similar to:</span></span>

  - <span data-ttu-id="419c1-115">1-ApplicationServer-1</span><span class="sxs-lookup"><span data-stu-id="419c1-115">1-ApplicationServer-1</span></span>

  - <span data-ttu-id="419c1-116">1-CentralMgmt-1</span><span class="sxs-lookup"><span data-stu-id="419c1-116">1-CentralMgmt-1</span></span>

  - <span data-ttu-id="419c1-117">1-WebServices-1</span><span class="sxs-lookup"><span data-stu-id="419c1-117">1-WebServices-1</span></span>
    
      - <span data-ttu-id="419c1-118">CollabContent</span><span class="sxs-lookup"><span data-stu-id="419c1-118">CollabContent</span></span>
    
      - <span data-ttu-id="419c1-119">CollabMetadata</span><span class="sxs-lookup"><span data-stu-id="419c1-119">CollabMetadata</span></span>
    
      - <span data-ttu-id="419c1-120">DataConf</span><span class="sxs-lookup"><span data-stu-id="419c1-120">DataConf</span></span>

<span data-ttu-id="419c1-121">然後 Web 會議服務會將 PowerPoint 投影片、白板、輪詢及附件之類的內容，儲存在 CollabContent 和 CollabMetadata 資料夾中 (位在 WebServices 資料夾中)。</span><span class="sxs-lookup"><span data-stu-id="419c1-121">The web conferencing service then stores content such as PowerPoint slides, whiteboards, polls, and attachments in the CollabContent and CollabMetadata folders, located in the WebServices folder.</span></span>

<span data-ttu-id="419c1-122">系統管理員必須設定檔案共用的權限，讓 RTC 群組擁有所需的讀取及寫入存取權。</span><span class="sxs-lookup"><span data-stu-id="419c1-122">The administrator must set permissions on the file share so that RTC groups have the necessary read and write access.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="419c1-p103">如果發生任何與權限相關的錯誤，請開啟拓撲產生器，下載並重新發行現有的拓撲。發行拓撲可驗證檔案共用權限，並依需要重設。</span><span class="sxs-lookup"><span data-stu-id="419c1-p103">If you encounter any errors with the permissions, open Topology Builder, download and republish the existing topology. Publishing the topology will verify the file share permissions and reset them if needed.</span></span>



</div>

<span data-ttu-id="419c1-125">您可以使用下列設定來管理儲存會議內容的方式：</span><span class="sxs-lookup"><span data-stu-id="419c1-125">You can use the following settings to manage how content is stored for a meeting:</span></span>

  - <span data-ttu-id="419c1-126">**ContentGracePeriod**，位於[Set-csconferencingconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration)，設定多久 web 會議內容會保留在伺服器上的會議結束之後。</span><span class="sxs-lookup"><span data-stu-id="419c1-126">**ContentGracePeriod**, located in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), sets how long web conferencing content will remain on the server after the meeting has ended.</span></span>

  - <span data-ttu-id="419c1-127">**MaxContentStorageMb**，位於[Set-csconferencingconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration)，設定單一會議期間所允許的儲存內容的檔案空間的量上限。</span><span class="sxs-lookup"><span data-stu-id="419c1-127">**MaxContentStorageMb**, located in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), sets the maximum amount of file space allowed for the storage of content during a single meeting.</span></span>

<span data-ttu-id="419c1-128">**MaxUploadFileSizeMb**就不會限制設定 Lync Web App 的檔案上傳。</span><span class="sxs-lookup"><span data-stu-id="419c1-128">**MaxUploadFileSizeMb** does not limit the file upload setting for Lync Web App.</span></span> <span data-ttu-id="419c1-129">Lync Web App 的檔案大小上傳限制設為大約 30 MB，而由 IIS 的 web.config 檔案所控制: / DataCollabWeb/Int\[Ext\]/Handler/web.config。若要設定 Lync Web App 的檔案大小上傳限制，請更新`maxRequestLength`和`maxAllowedContentLength`在 web.config 檔案中，如下所示。</span><span class="sxs-lookup"><span data-stu-id="419c1-129">The file size upload limit for Lync Web App is set to approximately 30MB and is controlled by the IIS web.config file: /DataCollabWeb/Int\[Ext\]/Handler/web.config. To configure the file size upload limit for Lync Web App, update `maxRequestLength` and `maxAllowedContentLength` in the web.config file as shown below.</span></span>

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

<span data-ttu-id="419c1-130">您必須更新 web.config 檔案的每個前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="419c1-130">You must update the web.config file for each Front End Server.</span></span>

</div>

<div>

## <a name="office-web-apps-server"></a><span data-ttu-id="419c1-131">Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="419c1-131">Office Web Apps Server</span></span>

<span data-ttu-id="419c1-132">若要使用這些新功能的系統管理員必須安裝 Office Web Apps Server，他們必須設定 Lync Server 2013 與 Office Web Apps Server 通訊。</span><span class="sxs-lookup"><span data-stu-id="419c1-132">In order to use these new capabilities administrators must install Office Web Apps Server and they must configure Lync Server 2013 to communicate with Office Web Apps Server.</span></span> <span data-ttu-id="419c1-133">這份文件提供如何設定為搭配 Office Web Apps Server 的 Lync Server 2013 的資訊。</span><span class="sxs-lookup"><span data-stu-id="419c1-133">This documentation provides information on how to configure Lync Server 2013 to work with Office Web Apps Server.</span></span> <span data-ttu-id="419c1-134">未提供什麼這份文件是有關如何安裝 Office Web Apps Server 的資訊。</span><span class="sxs-lookup"><span data-stu-id="419c1-134">What this documentation does not provide is information about how to install Office Web Apps Server.</span></span> <span data-ttu-id="419c1-135">安裝的詳細資訊，請參閱 Microsoft Office Web Apps 部署網站， <https://go.microsoft.com/fwlink/p/?linkid=257525>。</span><span class="sxs-lookup"><span data-stu-id="419c1-135">For installation details, see the Microsoft Office Web Apps Deployment website at <https://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span> <span data-ttu-id="419c1-136">該指南包括完整的 Office Web Apps Server 的必要資訊。</span><span class="sxs-lookup"><span data-stu-id="419c1-136">That guide includes complete prerequisite information for Office Web Apps Server.</span></span> <span data-ttu-id="419c1-137">請注意，應該不執行 Lync Server、 SQL Server 或任何其他伺服器應用程式的獨立電腦上安裝 Office Web Apps Server。</span><span class="sxs-lookup"><span data-stu-id="419c1-137">Note that Office Web Apps Server should be installed on a stand-alone computer that is not running Lync Server, SQL Server, or any other server application.</span></span> <span data-ttu-id="419c1-138">（您必須不會有任何版本的 Office 安裝在該電腦上。）用來執行 Office Web Apps Server 的任何電腦也必須有一組特定的軟體安裝 （包括.NET Framework 4.5 和 Windows PowerShell 3.0）。</span><span class="sxs-lookup"><span data-stu-id="419c1-138">(You must not have any version of Office installed on that computer.) Any computer used to run Office Web Apps Server must also have a specific set of software installed (including .NET Framework 4.5 and Windows PowerShell 3.0).</span></span> <span data-ttu-id="419c1-139">在 Microsoft Office Web Apps 部署網站中的詳細討論這些需求，以及設定憑證及網際網路資訊服務 (IIS) 的相關資訊<https://go.microsoft.com/fwlink/p/?linkid=257525>。</span><span class="sxs-lookup"><span data-stu-id="419c1-139">These requirements, along with information about configuring certificates and Internet Information Services (IIS), are discussed in detail in the Microsoft Office Web Apps Deployment website at <https://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="419c1-140">另請參閱</span><span class="sxs-lookup"><span data-stu-id="419c1-140">See Also</span></span>


[<span data-ttu-id="419c1-141">Lync Server 2013 中的 web 會議概觀</span><span class="sxs-lookup"><span data-stu-id="419c1-141">Overview of web conferencing in Lync Server 2013</span></span>](lync-server-2013-web-conferencing-overview.md)  
[<span data-ttu-id="419c1-142">Lync Server 2013 中的 web 會議的部署檢查表</span><span class="sxs-lookup"><span data-stu-id="419c1-142">Deployment checklist for web conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-web-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


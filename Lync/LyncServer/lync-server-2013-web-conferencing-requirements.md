---
title: Lync Server 2013： Web 會議需求
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
ms.openlocfilehash: 404ce93e841bbbefd62498a1dbb3da664eb927ff
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518250"
---
# <a name="web-conferencing-requirements-in-lync-server-2013"></a>Lync Server 2013 中的 Web 會議需求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-01-30_

如果您已選擇要啟用 Web 會議，則需規劃下列事項：

  - <span></span>  
    存取檔案存放區，以用來儲存 Web 會議內容。

  - <span></span>  
    與 Office Web Apps Server 整合，以便在會議期間共用 PowerPoint 檔案。

<div>

## <a name="file-store"></a>檔案存放區

Lync Server 2013 web 會議服務會儲存檔存放區中會議期間共用的內容。 在部署過程中，您必須指定要用來做為 Standard Edition server 或 Enterprise Edition 前端集區之檔案存放區的檔案共用。 您可以使用檔案存放區現有的檔案共用，也可以指定新的檔案共用，方法是指定檔案共用所在的檔案伺服器的完整功能變數名稱 (FQDN) ，以及新檔案共用的資料夾名稱。如需詳細資訊，請參閱拓撲產生器–定義前端的檔案存放區。 Web 會議服務會先對內容進行加密，然後才會將內容儲存在檔案存放區中。

Lync Server 2013 支援在直接連接儲存區 (DAS) 或儲存區域網路 (SAN) 上使用檔案共用，包括分散式檔案系統 (DFS) ，以及獨立磁碟容錯陣列 (RAID) 為檔案存放區。 在 Lync Server 部署嚮導定義檔案共用的位置之後，Lync Server 會在檔案共用中建立資料夾結構，類似下列所示：

  - 1-ApplicationServer-1

  - 1-CentralMgmt-1

  - 1-WebServices-1
    
      - CollabContent
    
      - CollabMetadata
    
      - DataConf

然後 Web 會議服務會將 PowerPoint 投影片、白板、輪詢及附件之類的內容，儲存在 CollabContent 和 CollabMetadata 資料夾中 (位在 WebServices 資料夾中)。

系統管理員必須設定檔案共用的權限，讓 RTC 群組擁有所需的讀取及寫入存取權。

<div>


> [!WARNING]  
> 如果發生任何與權限相關的錯誤，請開啟拓撲產生器，下載並重新發行現有的拓撲。發行拓撲可驗證檔案共用權限，並依需要重設。



</div>

您可以使用下列設定來管理儲存會議內容的方式：

  - **ContentGracePeriod**，位於 [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration)中，會設定在會議結束後，web 會議內容保留在伺服器上的時間。

  - **MaxContentStorageMb**，位於 [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration)中，會設定單一會議期間允許儲存內容的最大檔空間量。

**MaxUploadFileSizeMb** 不會限制 Lync Web App 的檔案上傳設定。 Lync Web App 的檔案大小上傳限制設定為大約30MB，且由 IIS web.config 檔案：/DataCollabWeb/Int \[ Ext \] /Handler/web.config 所控制。若要設定 Lync Web App 的檔案大小上傳限制，請更新， `maxRequestLength` 並 `maxAllowedContentLength` 在 web.config 檔中，如下所示。

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

您必須更新每一部前端伺服器的 web.config 檔案。

</div>

<div>

## <a name="office-web-apps-server"></a>Office Web Apps Server

若要使用這些新功能，管理員必須安裝 Office Web Apps Server，而且必須設定 Lync Server 2013，以與 Office Web Apps Server 通訊。 本檔提供如何設定 Lync Server 2013 以搭配 Office Web Apps Server 使用的資訊。 本檔不提供的資訊，是有關如何安裝 Office Web Apps Server 的資訊。 如需安裝詳細資訊，請參閱 Microsoft Office Web Apps 部署網站 <https://go.microsoft.com/fwlink/p/?linkid=257525> 。 該指南包含 Office Web Apps Server 的完整必要資訊。 請注意，Office Web Apps Server 應該安裝在未執行 Lync Server、SQL Server 或任何其他伺服器應用程式的獨立電腦上。  (您不能在該電腦上安裝任何版本的 Office。 ) 任何用來執行 Office Web Apps Server 的電腦也必須有一組特定的軟體安裝 (（包括 .NET Framework 4.5 和 Windows PowerShell 3.0) ）。 Microsoft Office Web Apps 部署網站會詳細討論這些需求，以及設定憑證和 Internet Information Services (IIS) 的相關資訊 <https://go.microsoft.com/fwlink/p/?linkid=257525> 。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的 web 會議概述](lync-server-2013-web-conferencing-overview.md)  
[Lync Server 2013 中的 web 會議部署檢查清單](lync-server-2013-deployment-checklist-for-web-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


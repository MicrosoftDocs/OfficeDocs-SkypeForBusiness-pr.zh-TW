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

# <a name="web-conferencing-requirements-in-lync-server-2013"></a>Lync Server 2013 的網路會議需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-01-30_

如果您已選擇啟用 [web 會議]，您必須規劃下列各項：

  - <span></span>  
    存取儲存網路會議內容所用的檔案存放區。

  - <span></span>  
    與 Office Web Apps Server 整合，這是為了在會議期間共用 PowerPoint 檔案所需要的。

<div>

## <a name="file-store"></a>檔案存放區

Lync Server 2013 網路會議服務會儲存在檔存放區中的會議期間共用的內容。 在部署過程中，您必須指定要用來做為標準版 server 或 Enterprise Edition 前端池之檔案存放區的檔案共用。 您可以將現有的檔案共用用於檔案存放區，或者您可以指定新的檔案共用，方法是指定檔案共用所在的檔案伺服器的完整功能變數名稱（FQDN），以及新檔案共用的資料夾名稱。如需詳細資訊，請參閱拓撲產生器-定義前端的檔案存放區。 網路會議服務會先加密內容，然後再將內容儲存在檔案存放區中。

Lync Server 2013 支援在直連儲存空間（DAS）或儲存區域網路（SAN）上使用檔案共用，包括分散式檔案系統（DFS），以及檔案存放區的獨立磁碟容錯陣列（RAID）。 在 Lync Server 部署嚮導定義檔案共用的位置之後，Lync Server 會在檔案共用中建立一個類似以下內容的資料夾結構：

  - 1-ApplicationServer-1

  - 1-CentralMgmt-1

  - 1-WebServices-1
    
      - CollabContent
    
      - CollabMetadata
    
      - DataConf

然後，web 會議服務會在 [WebServices] 資料夾中的 [CollabContent] 和 [CollabMetadata] 資料夾中儲存 PowerPoint 投影片、白板、投票及附件等內容。

系統管理員必須在檔案共用上設定許可權，才能讓 RTC 群組擁有必要的讀取和寫入存取權。

<div>


> [!WARNING]  
> 如果許可權有任何錯誤，請開啟 [拓撲建立器]，下載並重新發佈現有的拓撲。 發佈拓撲將會驗證檔案共用許可權，並視需要重設檔案。



</div>

您可以使用下列設定來管理會議內容的儲存方式：

  - **ContentGracePeriod**（位於[CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration)中）會設定在會議結束後，網路會議內容將在伺服器上保留多長時間。

  - **MaxContentStorageMb**（位於[CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration)中）會設定在單一會議期間儲存內容所允許的最大檔空間量。

**MaxUploadFileSizeMb**不會限制 Lync Web App 的 [檔案上傳] 設定。 Lync Web App 的檔案大小上傳限制是設定為 [大約 30MB]，且由 IIS web.config 檔案所控制：/DataCollabWeb/Int\[Ext\]/Handler/web.config。若要設定 Lync Web App 的檔案大小上傳限制， `maxRequestLength`請`maxAllowedContentLength`更新並放在 web.config 檔案中，如下所示。

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

您必須為每個前端伺服器更新 web.config 檔案。

</div>

<div>

## <a name="office-web-apps-server"></a>Office Web Apps 伺服器

若要使用這些新功能，系統管理員必須安裝 Office Web Apps 伺服器，而且必須設定 Lync Server 2013 與 Office Web Apps 伺服器進行通訊。 本檔提供如何設定 Lync Server 2013 以搭配 Office Web Apps 伺服器使用的相關資訊。 本檔不提供的內容是關於如何安裝 Office Web Apps Server 的資訊。 如需安裝的詳細資訊，請參閱 Microsoft Office Web Apps <http://go.microsoft.com/fwlink/p/?linkid=257525>部署網站。 該指南包括完整的 Office Web Apps 伺服器必備資訊。 請注意，Office Web Apps 伺服器應該安裝在未執行 Lync Server、SQL Server 或任何其他伺服器應用程式的獨立電腦上。 （您不得在該電腦上安裝任何版本的 Office）。任何用來執行 Office Web Apps Server 的電腦也必須安裝一組特定的軟體（包括 .NET Framework 4.5 和 Windows PowerShell 3.0）。 Microsoft Office Web Apps 部署網站中提供了這些需求，以及有關設定證書和網際網路資訊服務（IIS）的相關資訊<http://go.microsoft.com/fwlink/p/?linkid=257525>。

</div>

<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 中的 web 會議概述](lync-server-2013-web-conferencing-overview.md)  
[Lync Server 2013 的網路會議部署檢查清單](lync-server-2013-deployment-checklist-for-web-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


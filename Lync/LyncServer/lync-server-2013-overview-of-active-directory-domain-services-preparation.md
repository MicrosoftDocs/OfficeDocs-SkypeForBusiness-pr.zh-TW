---
title: Active Directory 網域服務準備的 Lync Server 2013： 概觀
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Active Directory Domain Services preparation
ms:assetid: cdd2a652-6a0d-4728-9950-3fcaa7a80066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398869(v=OCS.15)
ms:contentKeyID: 48185662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e2712859aa3268b70db9bd126f1ea17463955db
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216365"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-active-directory-domain-services-preparation-in-lync-server-2013"></a>Lync Server 2013 中的 Active Directory 網域服務準備的概觀

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-29_

若要準備您的 Lync Server 2013 部署的 Active Directory 網域服務，您必須以特定順序執行三個步驟。

下表說明準備 AD DS 的 Lync Server 時所需的步驟。

### <a name="active-directory-preparation-steps"></a>Active Directory 準備步驟

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>步驟</th>
<th>描述</th>
<th>執行位置</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1.</p></td>
<td><p><a href="lync-server-2013-preparing-the-active-directory-schema.md">準備 Lync Server 2013 中的 Active Directory 結構描述</a></p></td>
<td><p>將 Active Directory 架構延伸藉由新增新的類別和屬性所使用的 Lync Server。</p>
<p>執行一次每個樹系中部署 Lync Server 部署的位置。</p></td>
<td><p>針對要部署 Lync Server 每個樹系根網域中的結構描述主圖形。</p>
<div>

> [!NOTE]  
> 您不需要執行此步驟的根網域中，如果您的架構主機上有權限，但是您必須是 Schema Admins 群組中的根網域的成員，以及架構主機上的 Enterprise Admins 群組成員。 在資源樹系拓撲中，執行此步驟中，只能在資源樹系中，在任何使用者樹系中。 在中央樹系拓撲中，執行此步驟中，只能在中央樹系中，在任何使用者樹系中。


</div></td>
</tr>
<tr class="even">
<td><p>2.</p></td>
<td><p><a href="lync-server-2013-preparing-the-forest.md">準備樹系的 Lync Server 2013</a></p></td>
<td><p>會建立全域設定和萬用群組所使用的 Lync Server。</p>
<p>執行一次每個樹系中部署 Lync Server 部署的位置。</p></td>
<td><p>在 [Lync Server 將會部署每個樹系根網域。 若要執行此步驟，您必須是 Enterprise Admins 群組的成員。</p>
<div>

> [!NOTE]  
> 在資源樹系拓撲中，執行此步驟中，只能在資源樹系中，在任何使用者樹系中。 在中央樹系拓撲中，執行此步驟中，只能在中央樹系中，在任何使用者樹系中。


</div></td>
</tr>
<tr class="odd">
<td><p>3.</p></td>
<td><p><a href="lync-server-2013-preparing-domains.md">Lync Server 2013 的準備網域</a></p></td>
<td><p>新增權限萬用群組成員所使用的物件。</p>
<p>每個使用者網域或伺服器網域執行一次。</p>
<div>

> [!NOTE]  
> 如果您從 Lync Server 2010 移轉至 Lync Server 2013，[部署精靈可能表示網域準備已完成。 您不需要執行網域準備一次。 從 Lync Server 2010 to Lync Server 2013 未變更權限。


</div></td>
<td><p>在 [Lync Server 部署的位置的每個網域中的成員伺服器。 若要執行此步驟，您必須是 Domain Admins 群組的成員。</p></td>
</tr>
</tbody>
</table>


<div id="sectionSection0" class="section">

Lync Server 2013 中，例如 [Lync Server 2010]，儲存量的組態資訊的中央管理存放區中而不是 AD DS 中為已在 Office Communications Server 2007 R2 的案例。 不過，下列資訊會儲存在 AD DS 中：

  - **架構延伸模組**：
    
      - 使用者物件延伸
    
      - Office Communications Server 2007 R2 類別，以維持回溯相容性的副檔名

<!-- end list -->

  - **資料**（儲存在 Lync Server 延伸架構和現有的架構類別中）：
    
      - 使用者的 SIP 統一資源識別元 (URI) 及其他使用者設定
    
      - 回應群組與會議服務員等應用程式的連絡人物件
    
      - 中央管理存放區的指標
    
      - Kerberos 驗證帳戶 （選擇性的電腦物件）

在 Lync Server 2013 中，您委派的安裝和管理 RTCUniversalServerAdmins 萬用群組設定權限授與使該群組的成員可以安裝並在本機伺服器上啟動 Lync Server 2013 (伺服器已新增至之後拓撲中，發佈，而且可啟用）。 委派的使用者必須是本機系統管理員，他們會安裝並啟動 Lync Server 2013，但它們不需要成為 Domain Admins 群組的成員的電腦上。 您也可以授與指定組織單位 (Ou) 中的物件的權限，讓樹系準備時建立萬用群組的成員可以存取這些物件不是 Domain Admins 群組的成員。

針對新的 Lync Server 2013 的部署，全域設定必須儲存在 [Configuration] 容器。 如果您的組織從較早版本升級，仍必須在將系統容器中的全域設定，仍支援系統容器。

</div>

<div>

## <a name="see-also"></a>另請參閱


[準備 Lync Server 2013 中的 Active Directory 結構描述](lync-server-2013-preparing-the-active-directory-schema.md)  
[Active Directory 架構延伸模組、 類別及 Lync Server 2013 所使用的屬性](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)  


[準備樹系的 Lync Server 2013](lync-server-2013-preparing-the-forest.md)  
[Lync Server 2013 的準備網域](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


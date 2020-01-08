---
title: Lync Server 2013：Active Directory 網域服務支援
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Active Directory Domain Services support
ms:assetid: aeb62d5e-e424-473a-b795-9452150c98dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412831(v=OCS.15)
ms:contentKeyID: 48185136
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b264abefb1234892df355fee123dd6ce68b4dfb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974896"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-domain-services-support-in-lync-server-2013"></a>Lync Server 2013 中的 Active Directory 網域服務支援

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-11-07_

Lync Server 2013 使用中央管理儲存區來儲存伺服器與服務的設定資料，而不是依賴 Active Directory 網域服務來取得此資訊，就像過去的情況。 Lync Server 2013 仍會在 AD DS 中儲存下列專案：

  - **架構延伸**
    
      - 使用者物件延伸
    
      - Lync Server 2010 和 Office 通訊伺服器 2007 R2 類別的延伸，以維持與舊版支援版本的向後相容性

  - **資料**（儲存在 Lync Server 2013 延伸架構和現有的類別中）
    
      - 使用者 SIP URI 和其他使用者設定
    
      - 應用程式的連絡人物件（例如，回應群組應用程式與會議助理應用程式）
    
      - 針對向後相容性發佈的資料
    
      - 中央管理儲存體的服務控制點（SCP）
    
      - Kerberos 驗證帳戶（選擇性電腦物件）

本節說明 Lync Server 2013 的 AD DS 支援需求。 如需拓撲支援的詳細資料，請參閱支援檔中的[Lync Server 2013 支援的 Active Directory 拓撲](lync-server-2013-supported-active-directory-topologies.md)。

<div>

## <a name="supported-domain-controller-operating-systems"></a>支援的網網域控制站作業系統

Lync Server 2013 支援執行下列作業系統的網網域控制站：

  - Windows Server 2012 R2 作業系統

  - Windows Server 2012 作業系統

  - Windows Server 2008 R2 作業系統

  - Windows Server 2008 作業系統

  - Windows Server 2008 企業版32位

  - 32位或64位版本的 Window Server 2003 R2 作業系統

  - 32位或64位版本的 Windows Server 2003 作業系統

</div>

<div>

## <a name="forest-and-domain-functional-level"></a>林及網域功能層級

您必須將您將 Lync Server 2013 部署至 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008 或至少 Windows Server 2003 的網域功能層級的所有網域。

您在其中部署 Lync Server 2013 的所有林都必須在 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008 或至少 Windows Server 2003 的林功能層級引發。

</div>

<div>

## <a name="support-for-read-only-domain-controllers"></a>支援唯讀網網域控制站

Lync Server 2013 支援包括唯讀網網域控制站或唯讀通用類別目錄伺服器的 Active Directory 網域服務部署，只要有可寫入的網網域控制站可用。

</div>

<div>

## <a name="domain-names"></a>網功能變數名稱稱

Lync Server 不支援單一標示的網域。 例如，支援名為**contoso. local**的根網域的林，但不支援名為**local**的根網域。 如需詳細資訊，請參閱 Microsoft 知識庫文章300684：「使用單標籤 DNS 名稱設定 Windows 網域的相關資訊」 [http://go.microsoft.com/fwlink/p/?linkId=143752](http://go.microsoft.com/fwlink/p/?linkid=143752)。

<div>


> [!NOTE]  
> Lync Server 不支援重新命名網域。 如果您需要重新命名部署 Lync Server 的網域，您必須先卸載 Lync Server，然後重新命名網域，然後重新安裝 Lync Server。



</div>

</div>

<div>

## <a name="locked-down-adds-environments"></a>已鎖定 AD DS 環境

在鎖定的 AD DS 環境中，使用者和電腦物件通常是以停用許可權繼承的特定組織單位（Ou）來進行，以協助保護系統管理委派，並允許使用群組原則物件（Gpo）強制執行安全性原則。 Lync Server 2013 可以在鎖定的 Active Directory 環境中部署。 如需有關在鎖定環境中部署 Lync Server 所需功能的詳細資訊，請參閱部署檔中的[Lync server 2013 中的 [準備已鎖定的 Active Directory 網域服務](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)]。

</div>

</div>

<span> </span>

</div>

</div>

</div>


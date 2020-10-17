---
title: Lync Server 2013： Active Directory 網域服務支援
description: Lync Server 2013： Active Directory 網域服務支援。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory Domain Services support
ms:assetid: aeb62d5e-e424-473a-b795-9452150c98dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412831(v=OCS.15)
ms:contentKeyID: 48185136
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb2a85bab90557c28c4802721d4202f6188cb3f1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558679"
---
# <a name="active-directory-domain-services-support-in-lync-server-2013"></a>Lync Server 2013 中的 Active Directory 網域服務支援

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-11-07_

Lync Server 2013 使用中央管理存放區來儲存伺服器和服務的設定資料，而不是像過去這樣的資訊，而不是依賴此資訊的 Active Directory 網域服務。 Lync Server 2013 仍會在 AD DS 中儲存下列專案：

  - **架構擴充**
    
      - 使用者物件擴充
    
      - Lync Server 2010 和 Office 通訊伺服器 2007 R2 類別的延伸部分，以維護與舊版支援版本的回溯相容性

  - 儲存在 Lync Server 2013 擴充架構和現有類別中的**資料** () 
    
      - 使用者 SIP URI 及其他使用者設定
    
      - 應用程式的連絡人物件 (例如，回應群組應用程式和會議助理應用程式) 
    
      - 為回溯相容性發佈的資料
    
      - 中央管理存放區 (SCP) 的服務控制點
    
      - Kerberos 驗證帳戶 (選用的電腦物件) 

本節說明 Lync Server 2013 的 AD DS 支援需求。 如需拓撲支援的詳細資訊，請參閱支援檔中的 [支援的 Active Directory 拓撲（Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) ）。

<div>

## <a name="supported-domain-controller-operating-systems"></a>支援的網域控制站作業系統

Lync Server 2013 支援執行下列作業系統的網域控制站：

  - Windows Server 2012 R2 作業系統

  - Windows Server 2012 作業系統

  - Windows Server 2008 R2 operating system

  - Windows Server 2008 作業系統

  - Windows Server 2008 Enterprise 32-位

  - 32位或64位版本的 Windows Server 2003 R2 作業系統

  - 32位或64位版本的 Windows Server 2003 作業系統

</div>

<div>

## <a name="forest-and-domain-functional-level"></a>樹系和網域功能等級

您必須將您部署 Lync Server 2013 的所有網域，都提升為 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008 或至少為 Windows Server 2003 的網域功能等級。

您部署 Lync Server 2013 的所有樹系都必須引發為 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008 或至少為 Windows Server 2003 的樹系功能等級。

</div>

<div>

## <a name="support-for-read-only-domain-controllers"></a>Read-Only 網域控制站的支援

Lync Server 2013 支援包含唯讀網域控制站或唯讀通用類別目錄伺服器的 Active Directory 網域服務部署（只要有可用的可寫入網域控制站）。

</div>

<div>

## <a name="domain-names"></a>功能變數名稱

Lync Server 不支援單一標示的網域。 例如，根網域名稱為 **contoso.local** 的樹系是受支援的，名為 **local** 的根網域則不受支援。 如需詳細資訊，請參閱 Microsoft 知識庫文章300684：「如何針對具有單一標籤 DNS 名稱的網域設定 Windows」的相關資訊」 [https://go.microsoft.com/fwlink/p/?linkId=143752](https://go.microsoft.com/fwlink/p/?linkid=143752) 。

<div>


> [!NOTE]  
> Lync Server 不支援重新命名網域。 如果您需要重新命名已部署 Lync Server 的網域，您必須先卸載 Lync Server，然後重新命名網域，然後重新安裝 Lync Server。



</div>

</div>

<div>

## <a name="locked-down-adds-environments"></a>鎖定的 AD DS 環境

在鎖定的 AD DS 環境中，使用者和電腦物件通常會放在特定的組織單位中 () Ou 中，以停用許可權繼承，以協助保護系統管理委派及啟用群組原則物件 (Gpo) 的使用，以強制執行安全性原則。 Lync Server 2013 可部署在鎖定的 Active Directory 環境中。 如需在鎖定環境中部署 Lync Server 所需之專案的詳細資訊，請參閱部署檔中的在 [Lync Server 2013 中準備鎖定的 Active Directory 網域服務](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) 。

</div>

</div>

<span> </span>

</div>

</div>

</div>


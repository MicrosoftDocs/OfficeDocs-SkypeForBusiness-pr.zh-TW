---
title: 'Lync Server 2013: Active Directory 網域服務支援'
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
ms.openlocfilehash: 8bee58b0a35d2a3a322d799f2aadc9ba3b9c1bd9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199746"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="active-directory-domain-services-support-in-lync-server-2013"></a>Lync Server 2013 中的 active Directory 網域服務支援

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-11-07_

Lync Server 2013 使用的中央管理存放區來儲存伺服器和服務，而不要依賴此資訊，如同在過去的 Active Directory 網域服務的組態資料。 Lync Server 2013 仍然會儲存在 AD DS 中的下列：

  - **架構延伸模組**
    
      - 使用者物件延伸
    
      - Lync Server 2010 和 Office Communications Server 2007 R2 類別，以維持與舊版回溯相容性的延伸支援的版本

  - **資料**（儲存在 Lync Server 2013 延伸架構和現有類別中）
    
      - 使用者的 SIP URI 和其他使用者設定
    
      - 應用程式 （例如，回應群組應用程式與會議服務員應用程式） 的連絡人物件
    
      - 發行的回溯相容性資料
    
      - 服務控制點 (SCP) 的中央管理存放區
    
      - Kerberos 驗證帳戶 （選擇性的電腦物件）

本節說明 Lync Server 2013 的 AD DS 支援需求。 如需詳細資訊的拓樸的相關支援，請參閱支援文件中的[Lync Server 2013 中支援的 Active Directory 拓撲](lync-server-2013-supported-active-directory-topologies.md)。

<div>

## <a name="supported-domain-controller-operating-systems"></a>支援的網域控制站作業系統

Lync Server 2013 支援執行下列作業系統的網域控制站：

  - Windows Server 2012 R2 作業系統

  - Windows Server 2012 作業系統

  - Windows Server 2008 R2 operating system

  - Windows Server 2008 作業系統

  - Windows Server 2008 Enterprise 32 位元

  - 32 位元或 64 位元版本的 Window Server 2003 R2 作業系統

  - 32 位元或 64 位元版本的 Windows Server 2003 作業系統

</div>

<div>

## <a name="forest-and-domain-functional-level"></a>樹系和網域功能等級

您必須提高您將 Lync Server 2013 部署至 Windows Server 2012 R2、 Windows Server 2012、 Windows Server 2008 R2、 Windows Server 2008] 或是在網域功能等級的所有網域最低的 Windows Server 2003。

您將部署 Lync Server 2013 的所有樹系必須引發為 Windows Server 2012 R2、 Windows Server 2012、 Windows Server 2008 R2、 Windows Server 2008] 或是在樹系功能等級最低的 Windows Server 2003。

</div>

<div>

## <a name="support-for-read-only-domain-controllers"></a>支援唯讀網域控制站

Lync Server 2013 支援包含唯讀網域控制站或唯讀通用類別目錄伺服器的 Active Directory 網域服務部署，只要有可用的可寫入的網域控制站。

</div>

<div>

## <a name="domain-names"></a>網域名稱

Lync Server 不支援單一標示的網域。 例如，根網域名稱為 **contoso.local** 的樹系是受支援的，名為 **local** 的根網域則不受支援。 如需詳細資訊，請參閱 Microsoft 知識庫文章 300684，「 設定資訊視窗具有單一標籤 DNS 名稱的網域 」， [https://go.microsoft.com/fwlink/p/?linkId=143752](https://go.microsoft.com/fwlink/p/?linkid=143752)。

<div>


> [!NOTE]  
> Lync Server 不支援重新命名的網域。 如果您需要重新命名其中部署 Lync Server 的網域，您需要先解除安裝 Lync Server]，然後重新命名網域，並再重新安裝 Lync Server。



</div>

</div>

<div>

## <a name="locked-down-adds-environments"></a>鎖定 AD DS 環境

在鎖定的 AD DS 環境中，User 及 Computer 物件通常會放在特定組織單位 (Ou) 中停用來協助保護系統管理委派，並啟用使用群組原則物件 (Gpo) 強制執行權限繼承安全性原則。 可以在鎖定的 Active Directory 環境中部署 Lync Server 2013。 如需什麼是必要鎖定的環境中部署 Lync Server 的詳細資訊，請參閱部署文件中的[準備鎖定的 Active Directory 網域服務在 Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) 。

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013：建立主控 Exchange UM 的連絡人物件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create contact objects for hosted Exchange UM
ms:assetid: a39be52f-488a-4523-ad5f-ce1f0d681959
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412765(v=OCS.15)
ms:contentKeyID: 48185045
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c783a79c6d3ed3cd0af47d53d136a47585cb94d0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205629"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-contact-objects-for-hosted-exchange-um-in-lync-server-2013"></a>在 Lync Server 2013 中建立主控 Exchange UM 的連絡人物件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-24_

下列程式說明如何建立自動語音應答 (AA) 或訂閱者存取 (SA) 連絡人物件，以供主控 Exchange 整合通訊 (UM) 。

如需詳細資訊，請參閱規劃檔中的 [主控 Exchange 連絡人物件管理（Lync Server 2013](lync-server-2013-hosted-exchange-contact-object-management.md) ）。

如需設定連絡人物件的詳細資訊，請參閱 Lync Server 管理命令介面檔中的下列 Cmdlet：

  - [New-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/New-CsExUmContact)

  - [Set-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/Set-CsExUmContact)

<div class=" ">


> [!IMPORTANT]  
> 在 Lync Server 2013 的連絡人物件可供主控 Exchange UM 啟用之前，必須先部署適用于這些物件的主控語音信箱原則。 如需詳細資訊，請參閱 <A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 中的主控語音信箱原則</A>。



</div>

<div>

## <a name="to-create-aa-or-sa-contact-objects-for-hosted-exchange-um"></a>為主控 Exchange UM 建立 AA 或 SA 連絡人物件

1.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行 New-CsExUmContact Cmdlet，以建立部署所需的任何連絡人物件。 例如，執行下列程式以建立 AA 及 SA 連絡人物件：
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumaa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101" -AutoAttendant $True
       ```
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumsa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101"
       ```
    
    這些範例會設定下列參數：
    
      - **SipAddress** 會指定連絡人物件的 SIP 位址。 這必須是尚未用來設定 Active Directory 網域服務中的使用者或連絡人物件的位址。 此值必須是 "sip： \< *sip address*" 的格式， \> 如先前的範例所示。
    
      - **RegistrarPool** 會指定執行註冊服務之集區的完整功能變數名稱 (FQDN) 。
        
        <div class=" ">
        

        > [!NOTE]  
        > 在 Lync Server 2013 之前，無法將 Exchange UM 連絡人物件移至屬於 Lync Server 2013 部署一部分的集區。

        
        </div>
    
      - **OU** 會指定此連絡人物件所在的 Active Directory 組織單位。
    
      - **DisplayNumber** 會指定連絡人物件的電話號碼。 每個連絡人物件的電話號碼都必須是唯一的。
    
      - **AutoAttendant** 會指定連絡人物件是否為自動語音應答。 自動語音應答提供一組語音提示，讓來電者能夠流覽電話系統，並抵達他們想要聯絡的方。 值為 **False** (此參數的預設) 會指出訂戶存取連絡人物件。

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013：建立主控 Exchange UM 的聯絡人物件
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
ms.openlocfilehash: 358b595fceb05a377c59479b0a08e100bffb318a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740343"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-contact-objects-for-hosted-exchange-um-in-lync-server-2013"></a>在 Lync Server 2013 中建立主控 Exchange UM 的聯絡人物件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-24_

下列程式說明如何針對託管 Exchange 整合通訊（UM）建立自動語音應答（AA）或訂閱者存取（SA）連絡人物件。

如需詳細資訊，請參閱規劃檔中的[Lync Server 2013 中託管的 Exchange 連絡人物件管理](lync-server-2013-hosted-exchange-contact-object-management.md)。

如需有關設定連絡人物件的詳細資訊，請參閱適用于下列 Cmdlet 的 Lync Server 管理命令介面檔：

  - [新-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/New-CsExUmContact)

  - [Set-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/Set-CsExUmContact)

<div class=" ">


> [!IMPORTANT]  
> 在 Lync Server 2013 連絡人物件可供託管 Exchange UM 使用之前，必須先部署適用于它們的託管語音信箱原則。 如需詳細資訊，請參閱<A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 中託管的語音信箱原則</A>。



</div>

<div>

## <a name="to-create-aa-or-sa-contact-objects-for-hosted-exchange-um"></a>若要為託管 Exchange UM 建立 AA 或 SA 連絡人物件

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行新的 CsExUmContact Cmdlet，以建立您部署所需的任何連絡人物件。 例如，請執行下列動作來建立 AA 與 SA 連絡人物件：
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumaa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101" -AutoAttendant $True
       ```
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumsa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101"
       ```
    
    這些範例會設定下列參數：
    
      - **SipAddress**指定連絡人物件的 SIP 位址。 此位址必須是尚未用來設定 Active Directory 網域服務中的使用者或連絡人物件的位址。 此值必須是「sip：\<*sip 位址*\>」格式，如先前的範例所示。
    
      - **RegistrarPool**指定運行註冊服務之池的完整功能變數名稱（FQDN）。
        
        <div class=" ">
        

        > [!NOTE]  
        > 在 Lync Server 2013 之前，無法將 Exchange UM 連絡人物件移到屬於 Lync Server 2013 部署的 pool。

        
        </div>
    
      - **OU** ：指定此連絡人物件將位於哪個 Active Directory 組織單位。
    
      - **DisplayNumber**指定連絡人物件的電話號碼。 每個連絡人物件的電話號碼都必須是唯一的。
    
      - [自動**助理**] 可指定連絡人物件是否為自動語音應答。 自動語音應答會提供一組語音提示，讓呼叫者流覽電話系統，並到達他們想要聯絡的對方。 此參數的**False**值（預設值）表示訂閱者存取連絡人物件。

</div>

</div>

<span> </span>

</div>

</div>

</div>


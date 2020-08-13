---
title: Lync Server 2013：主控 Exchange 連絡人物件管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange Contact object management
ms:assetid: eead9d76-bc4f-4c1c-9779-683cb7a88410
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412978(v=OCS.15)
ms:contentKeyID: 48185748
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ede940e1126660aaae89fe6552f050632f841b8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198726"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-contact-object-management-in-lync-server-2013"></a>Lync Server 2013 中的主控 Exchange 連絡人物件管理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-25_

您必須針對跨單位部署中的每個自動語音應答號碼和使用者存取號碼，設定連絡人物件。

若要與主控 Exchange UM 整合，ocsumutil.exe 無法用來管理連絡人物件，因為這取決於 Active Directory Exchange UM 設定。 在跨單位部署中，Lync Server 2013 和主控 Exchange UM 是安裝在不同的樹系中，彼此之間不具任何信任。 基於安全性原因，Lync Server 2013 系統管理員無法直接存取 Exchange UM Active Directory 設定。 因此，Lync Server 2013 提供不同的模型，用以管理 Lync Server 2013 和主控 Exchange UM 服務可存取的 *共用 SIP 位址空間* 中的連絡人物件。

<div>

## <a name="hosted-contact-object-workflow"></a>主控的連絡人物件工作流程

以下是與託管的 Exchange 租使用者管理員搭配使用以管理連絡人物件的一般步驟：

1.  Exchange 管理員要求 Exchange UM 訂戶存取和自動語音應答連絡人物件的電話號碼。

2.  Lync Server 2013 系統管理員會為每個電話號碼建立連絡人物件，並將主控的語音信箱原則指派給每個連絡人物件。

3.  Lync Server 2013 系統管理員會為 Exchange 系統管理員提供電話號碼。

4.  Exchange 管理員會將電話號碼指派給適當的 Exchange UM 撥號對應表，以供自動語音應答和訂戶存取。

<div>


> [!NOTE]  
> 您不需要在連絡人物件上設定任何 Lync Server 2013 撥號對應表設定，就像內部部署部署一樣。



</div>

</div>

<div>

## <a name="configuring-hosted-contact-objects"></a>設定主控的連絡人物件

<div>


> [!NOTE]  
> 在 Lync Server 2013 的連絡人物件可供主控 Exchange UM 啟用之前，必須先部署適用于這些物件的主控語音信箱原則。 原則可以是全域、網站層級或個別使用者範圍，只要套用至您想要啟用的連絡人物件。 如需詳細資訊，請參閱 <A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 中的主控語音信箱原則</A>。



</div>

若要在跨部署部署中設定主控的自動語音應答和訂戶存取連絡人物件，您必須使用下列 Cmdlet：

  - **New-CsExUmContact** 會為主控的 UM 建立新的連絡人物件。

  - **Set-CsExUmContact** 會修改主控 Exchange UM 的現有連絡人物件。

下列範例會建立自動語音應答連絡人物件：

    New-CsExUmContact -SipAddress sip:exumaa1@fabrikam.com -RegistrarPool RedmondPool.litwareinc.com -OU "OU=ExUmContacts,DC=litwareinc,DC=com" -DisplayNumber 2065559876 -AutoAttendant $True

此範例會使用 SIP 位址 sip:exumaa1@fabrikam.com 來建立新的 Exchange UM 連絡人物件。 Lync Server 2013 註冊服務所在的集區名稱是 RedmondPool.litwareinc.com。 儲存此資訊的 Active Directory 組織單位為 OU = ExUmContacts，DC = litwareinc，DC=com。 連絡人物件的電話號碼是2065554567。 Optional-AutoAttendant $True 參數會指定此物件為自動語音應答連絡人物件。 將-AutoAttendant 參數設定為 False (default) 會指定訂戶存取連絡人物件。

如需 New-CsExUmContact 和 Set-CsExUmContact Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔。

</div>

</div>

<span> </span>

</div>

</div>

</div>


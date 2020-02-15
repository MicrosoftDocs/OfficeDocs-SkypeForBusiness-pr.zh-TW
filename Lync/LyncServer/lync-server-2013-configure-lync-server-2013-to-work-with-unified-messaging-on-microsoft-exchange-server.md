---
title: Lync Server 2013： 設定 Lync Server 2013 以使用 Microsoft Exchange Server 上整合通訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server
ms:assetid: 1098ae4d-f57f-44f3-804e-39889d9fc14e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398193(v=OCS.15)
ms:contentKeyID: 48183430
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65908f1b142c72f584c48493023803e5dfd56208
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030997"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server"></a>設定 Lync Server 2013 來使用 Microsoft Exchange Server 上整合通訊

</div>

<div id="mainSection">

<div id="mainBody">

_**上次修改主題：** 2013年-04-03_

這個步驟需要 Exchange UM 整合公用程式 (OcsUmUtil.exe)。 這項工具位在 Lync Server 2013 伺服器上。\\Program Files\\通用檔案\\Microsoft Lync Server 2013\\支援資料夾。

<div>

## <a name="running-the-exchange-um-integration-utility"></a>執行 Exchange UM 整合公用程式

Exchange UM 整合公用程式必須從具有下列特性的使用者帳戶執行：

  - RTCUniversalServerAdmins 與 RtcUniversalUserAdmins 群組的成員資格 (包括讀取 Exchange Server Unified Messaging 設定的權限)。

  - 使用者的權限的網域內指定的組織單位 (OU) 容器中建立連絡人物件。

當您執行 Exchange UM 整合公用程式時，它會執行下列工作：

  - 針對 Enterprise Voice 使用者所要使用的每一個自動語音應答和訂戶存取號碼來建立連絡人物件。

  - 確認每個企業語音撥號對應表計劃名稱符合其對應整合通訊 (UM) 撥號對應表計劃電話內容。 此比對是 UM 撥號對應表在舊版 Exchange*早*於 Exchange 2010 Service Pack 1 (SP1) 上執行時，才需要。

> [!IMPORTANT]
> 之前執行 Exchange UM 整合公用程式，請確定您已執行下列：
> <ul>
> <li><p>建立一或多個 Exchange UM 撥號對應表計劃，Exchange 產品文件中所述。</p>
> <p>Microsoft Exchange Server 2010，請參閱&quot;Create a UM Dial Plan&quot;在<a href="http://go.microsoft.com/fwlink/p/?linkid=186177">http://go.microsoft.com/fwlink/p/?linkId=186177</a>。</p>
> <p>Microsoft Exchange Server 2007 Service Pack 1 (SP1)，請參閱&quot;如何建立整合通訊 SIP URI 撥號對應表規劃&quot;在<a href="http://go.microsoft.com/fwlink/p/?linkid=185771">http://go.microsoft.com/fwlink/p/?linkId=185771</a>。</p></li>
> <li><p>建立一或多個對應 Lync Server 撥號對應表，在<a href="lync-server-2013-create-a-dial-plan.md">建立撥號對應表 Lync Server 2013 中的</a>所述。</p></li>
> <ul><li>如果您使用的是舊，超出了 Microsoft Exchange Server 2010 SP1 的 Exchange 版本，您必須在 [Lync Server 2013 撥號對應表規劃<STRONG>簡單名稱</STRONG>] 欄位中輸入對應的 Exchange 整合通訊 (UM) SIP 撥號對應表的完整的網域名稱 (FQDN)。 如果您使用 Microsoft Exchange Server 2010 SP1 或最新 service pack，並不需要此撥號對應表計劃名稱比對。</li></ul>
> <li>請建立一個自動語音應答，並且確定訂戶存取號碼和自動語音應答號碼的格式都是 E.164。</li></ul>


<div>

## <a name="to-run-the-exchange-um-integration-utility"></a>若要執行 Exchange UM 整合公用程式

1.  在前端伺服器上，開啟 [命令提示字元並輸入**cd %commonprogramfiles%\\Microsoft Lync Server 2013\\支援**，然後按 ENTER 鍵。

2.  輸入 **OcsUmUtil.exe**，然後按 ENTER。

3.  按一下 **[載入資料]** 以找出所有受信任的 Exchange 樹系。

4.  在 **[SIP 撥號對應表]** 清單中，選取您要為它建立連絡人物件的 UM SIP 撥號對應表，然後按一下 **[新增]**。

5.  在 **[連絡人]** 方塊中，接受預設的組織單位，或按一下 **[瀏覽]** 來啟動 **[OU 選擇器]**。在 **[OU 選擇器]** 方塊中，您可以選擇一個 OU，再按一下 **[確定]**，或者您可以按一下 **[建立新的 OU]**，在根目錄底下或網域中其他任何 OU 底下建立新的組織單位 (例如，"OU=RTC Special Accounts,DC=fourthcoffee,DC=com")，然後按一下 **[確定]**。
    
    <div>
    

    > [!NOTE]  
    > 您所選取或建立之 OU 的辨別名稱 (DN)，現在會在 <STRONG>[組織單位]</STRONG> 方塊中顯示。

    
    </div>

6.  在 **[名稱]** 方塊中，接受預設的撥號對應表名稱，或者為您要建立的連絡人物件輸入新的顯示名稱。
    
    <div>
    

    > [!NOTE]  
    > 例如，如果您要建立訂閱者存取連絡人物件，可以直接命名為「訂閱者存取」。

    
    </div>

7.  在 **[SIP 位址]** 方塊中，接受預設 SIP 位址或輸入新的 SIP 位址。
    
    <div>
    

    > [!NOTE]  
    > 如果輸入新的 SIP 位址，必須以 <STRONG>SIP:</STRONG> 開頭 (也就是 "SIP:"，包括冒號)。

    
    </div>

8.  在**伺服器或集區**] 清單中，選取 Standard Edition server 或前端集區中的連絡人物件是啟用。
    
    <div>
    

    > [!NOTE]  
    > 您選取的集區最好是與啟用 Enterprise Voice 與 Exchange UM 之使用者部署的集區相同。

    
    </div>

9.  在 **[電話號碼]** 清單中，選取 **[輸入電話號碼]** 或 **[從 Exchange UM 使用此整合通訊接駁電話號碼]**，然後輸入電話號碼。

10. 在 **[連絡人類型]** 清單中，選取您要建立的連絡人類型，然後按一下 **[確定]**。

11. 為您要建立的其他連絡人物件重複步驟 1 到 10。
    
    <div>
    

    > [!NOTE]  
    > 您應該為每個自動語音應答至少建立一個連絡人。如果您想要提供外部存取，也需要具備「訂戶存取」連絡人，並指定直接向內撥號 (DID) 號碼。

    
    </div>

</div>

若要確認已經建立了連絡人物件，請開啟 [Active Directory 使用者及電腦]，再選取建立物件的 OU。連絡人物件應會在詳細資料窗格中顯示。

</div>

</div>

<span> </span>

</div>

</div>

</div>


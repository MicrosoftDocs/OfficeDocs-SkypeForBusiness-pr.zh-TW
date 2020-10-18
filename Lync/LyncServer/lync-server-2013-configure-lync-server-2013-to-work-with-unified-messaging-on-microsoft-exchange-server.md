---
title: Lync Server 2013：將 Lync Server 2013 設定為使用 Microsoft Exchange Server 上的整合通訊
description: Lync Server 2013：將 Lync Server 2013 設定為使用 Microsoft Exchange Server 上的整合通訊。
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
ms.openlocfilehash: 05ef2902ffc03b14e04b378a2ef18e03c8c58372
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578039"
---
# <a name="configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server"></a>設定 Lync Server 2013，以搭配 Microsoft Exchange Server 上的整合通訊使用

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

_**主題上次修改日期：** 2013-04-03_

這個步驟需要 Exchange UM 整合公用程式 (OcsUmUtil.exe)。 此工具位於中的 Lync Server 2013 伺服器上。 \\Program Files \\ 常見檔案 \\ Microsoft Lync Server 2013 \\ 支援資料夾。

<div>

## <a name="running-the-exchange-um-integration-utility"></a>執行 Exchange UM 整合公用程式

Exchange UM 整合公用程式必須從具有下列特性的使用者帳戶執行：

  - RTCUniversalServerAdmins 與 RtcUniversalUserAdmins 群組的成員資格 (包括讀取 Exchange Server Unified Messaging 設定的權限)。

  - 網域內的使用者權限，可在指定的組織單位 (OU) 容器中建立連絡人物件。

當您執行 Exchange UM 整合公用程式時，它會執行下列工作：

  - 針對 Enterprise Voice 使用者所要使用的每一個自動語音應答和訂戶存取號碼來建立連絡人物件。

  - 驗證每個 Enterprise Voice 撥號對應表的名稱是否符合其對應的整合通訊 (UM) 撥號對應表電話內容。 只有當 UM 撥號對應表在 exchange 2010 Service Pack 1 (SP1) 上的 *exchange 版本* 上執行時，才需要這種對應。

> [!IMPORTANT]
> 在執行 Exchange UM 整合公用程式之前，請確定您已完成下列作業：
> <ul>
> <li><p>如 Exchange 產品檔中所述，建立一或多個 Exchange UM 撥號對應表。</p>
> <p>如需 Microsoft Exchange Server 2010，請參閱 &quot; Create a UM 撥號對應表 &quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=186177">https://go.microsoft.com/fwlink/p/?linkId=186177</a> 。</p>
> <p>如需 Microsoft Exchange Server 2007 Service Pack 1 (SP1) ，請參閱 how &quot; To Create a 整合通訊 SIP URI 撥號對應表， &quot; 網址為 <a href="https://go.microsoft.com/fwlink/p/?linkid=185771">https://go.microsoft.com/fwlink/p/?linkId=185771</a> 。</p></li>
> <li><p>建立一或多個對應的 Lync Server 撥號對應表，如在 <a href="lync-server-2013-create-a-dial-plan.md">Lync Server 2013 中建立撥號</a>對應表所述。</p></li>
> <ul><li>如果您使用的是舊于 Microsoft Exchange Server 2010 SP1 版本的 Exchange，則必須在 [Lync Server 2013 撥號對應表 <STRONG>簡易名稱</STRONG> ] 欄位中輸入對應 Exchange 整合通訊 (UM) SIP 撥號對應表的完整功能變數名稱 (FQDN) 。 如果您使用的是 Microsoft Exchange Server 2010 SP1 或最新的 service pack，則不需要此撥號對應表名稱比對。</li></ul>
> <li>請建立一個自動語音應答，並且確定訂戶存取號碼和自動語音應答號碼的格式都是 E.164。</li></ul>


<div>

## <a name="to-run-the-exchange-um-integration-utility"></a>若要執行 Exchange UM 整合公用程式

1.  在前端伺服器上，開啟命令提示字元，並輸入 **cd%CommonProgramFiles% \\ Microsoft Lync Server 2013 \\ 支援**，然後按 ENTER。

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

8.  在 [ **伺服器或集** 區] 清單中，選取要啟用連絡人物件的 Standard Edition 伺服器或前端集區。
    
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


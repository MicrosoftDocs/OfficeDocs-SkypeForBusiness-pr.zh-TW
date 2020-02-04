---
title: Lync Server 2013：設定 Lync Server 2013 以搭配 Microsoft Exchange Server 上的 Unified Messaging 使用
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
ms.openlocfilehash: 985b2d286f65be2353c2ace0d59872f4d0fc47ad
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729743"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server"></a>設定 Lync Server 2013 以搭配 Microsoft Exchange Server 上的 Unified Messaging 使用

</div>

<div id="mainSection">

<div id="mainBody">

_**主題上次修改日期：** 2013-04-03_

此步驟需要 Exchange UM 整合實用程式（OcsUmUtil）。 此工具位於 Lync Server 2013 伺服器上的。\\Program files\\常見檔案\\Microsoft Lync Server 2013\\支援資料夾。

<div>

## <a name="running-the-exchange-um-integration-utility"></a>執行 Exchange UM 整合公用程式

Exchange UM 整合公用程式必須從具有下列特性的使用者帳戶執行：

  - RTCUniversalServerAdmins 和 RtcUniversalUserAdmins 群組中的成員資格（包含讀取 Exchange Server 整合通訊設定的許可權）。

  - 網域中的使用者權利，可在指定的組織單位（OU）容器中建立連絡人物件。

當您執行 Exchange UM 整合公用程式時，會執行下列任務：

  - 針對企業語音使用者所要使用的每個自動助理和使用者存取號碼建立連絡人物件。

  - 驗證每個企業語音撥號方案的名稱是否符合其對應的 [統一訊息（UM）撥號方案電話] 內容。 只有在 Exchange 2010 Service Pack 1 （SP1）*之前*的 exchange 版本上執行 UM 撥號方案時，才能使用這個相符。

> [!IMPORTANT]
> 在執行 Exchange UM 整合公用程式前，請確定您已完成下列作業：
> <ul>
> <li><p>建立一或多個 Exchange UM 撥號方案，如 Exchange 產品檔中所述。</p>
> <p>若為 Microsoft Exchange Server 2010， &quot;請參閱在<a href="http://go.microsoft.com/fwlink/p/?linkid=186177">http://go.microsoft.com/fwlink/p/?linkId=186177</a>建立 UM&quot;撥號方案。</p>
> <p>如果您使用的是 Microsoft Exchange Server 2007 Service Pack 1 （ &quot;SP1），請參閱如何在<a href="http://go.microsoft.com/fwlink/p/?linkid=185771">http://go.microsoft.com/fwlink/p/?linkId=185771</a>建立整合通訊&quot; SIP URI 撥號計畫。</p></li>
> <li><p>如在<a href="lync-server-2013-create-a-dial-plan.md">Lync server 2013 中建立撥號方案</a>中所述，建立一個或多個對應的 Lync server 撥號方案。</p></li>
> <ul><li>如果您使用的 Exchange 版本早于 Microsoft Exchange Server 2010 SP1，您必須在 Lync Server 2013 撥號方案 [<STRONG>簡易名稱</STRONG>] 欄位中輸入對應 Exchange 整合訊息（UM） SIP 撥號方案的完整功能變數名稱（FQDN）。 如果您使用的是 Microsoft Exchange Server 2010 SP1 或最新的 service pack，則不需要這種撥號方案名稱相符。</li></ul>
> <li>建立自動助理，並確認使用者存取號碼和自動助理號碼的格式為：164。</li></ul>


<div>

## <a name="to-run-the-exchange-um-integration-utility"></a>若要執行 Exchange UM 整合公用程式

1.  在前端伺服器上，開啟命令提示字元，然後輸入**cd% CommonProgramFiles%\\Microsoft Lync Server 2013\\支援**，然後按 enter。

2.  輸入**OcsUmUtil**，然後按 enter。

3.  按一下 [**載入資料**] 以尋找所有受信任的 Exchange 目錄林。

4.  在 [ **SIP 撥號方案**] 清單中，選取您要為其建立連絡人物件的 UM SIP 撥號方案，然後按一下 [**新增**]。

5.  在 [**連絡人**] 方塊中，接受預設組織單位，或按一下 **[流覽]** 以啟動**OU 選擇器**。 在 [ **OU 選擇器**] 方塊中，您可以選取一個 ou 並按一下 **[確定]**，或按一下 [**建立新的 OU** ]，在網域的根目錄或任何其他 ou （例如，「OU = RTC 特殊帳戶、dc =.、dc = com」）中建立新的組織單位，然後按一下 **[確定]**。
    
    <div>
    

    > [!NOTE]  
    > 您已選取或建立之 OU 的辨識名稱（DN）現在會顯示在 [<STRONG>組織單位</STRONG>] 方塊中。

    
    </div>

6.  在 [**名稱**] 方塊中，接受預設的撥號計畫名稱，或針對您要建立的連絡人物件輸入新的顯示名稱。
    
    <div>
    

    > [!NOTE]  
    > 例如，如果您要建立訂閱者 access 連絡人物件，可能只需將其命名為訂閱者存取。

    
    </div>

7.  在 [ **SIP 位址**] 方塊中，您可以接受預設的 sip 位址，或輸入新的 sip 位址。
    
    <div>
    

    > [!NOTE]  
    > 如果您輸入新的 SIP 位址，它必須以<STRONG>SIP 開頭：</STRONG> （也就是「SIP：」包括冒號）。

    
    </div>

8.  在 [**伺服器] 或 [池**] 清單中，選取要啟用連絡人物件的標準版伺服器或 [前端] 池。
    
    <div>
    

    > [!NOTE]  
    > 最好的是，您所選取的 [池] 就是部署啟用企業語音和 Exchange UM 之使用者的同一個池。

    
    </div>

9.  在 [**電話號碼**] 清單中，選取 [**輸入電話號碼**] 或 [**從 Exchange UM 使用這個試驗號碼**]，然後輸入電話號碼。

10. 在 [**連絡人類型**] 清單中，選取您要建立的連絡人類型，然後按一下 **[確定]**。

11. 針對您想要建立的其他連絡人物件，重複步驟1到10。
    
    <div>
    

    > [!NOTE]  
    > 您至少應該為每個自動語音助理建立一個連絡人。 如果您想要外部存取，您也需要訂閱者存取連絡人，並指定直接撥出電話（已有）號碼。

    
    </div>

</div>

若要確認已建立連絡人物件，請開啟 [Active Directory 使用者和電腦]，然後選取在其中建立物件的 OU。 連絡人物件應該會出現在 [詳細資料] 窗格中。

</div>

</div>

<span> </span>

</div>

</div>

</div>


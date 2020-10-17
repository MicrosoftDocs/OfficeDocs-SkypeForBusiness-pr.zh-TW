---
title: Lync Server 2013：在 Microsoft Exchange 上設定整合通訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Unified Messaging on Microsoft Exchange
ms:assetid: 07547968-c59b-4dde-ace4-9fd286933759
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398129(v=OCS.15)
ms:contentKeyID: 48183311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b39c10a3fb590acc99771663f5f6e23e3c3095e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520220"
---
# <a name="configure-unified-messaging-on-microsoft-exchange-for-lync-server-2013"></a>在 Microsoft Exchange 上設定 Lync Server 2013 的整合通訊

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-24_

本主題說明如何在 Microsoft Exchange Server 上設定 Exchange 整合通訊 (UM) ，以與 Enterprise Voice 搭配使用。

<div>


> [!NOTE]  
> 本主題中的 Cmdlet 範例會提供 exchange 2007 版本的 Exchange 管理命令介面的語法。 如果您正在執行 Exchange 2010 或 Exchange 2013，請參閱參考的適當檔。



</div>

<div>

## <a name="to-configure-a-server-running-exchange-server-um"></a>設定執行 Exchange Server UM 的伺服器

1.  針對每個企業語音位置設定檔，建立 UM 會話初始通訊協定 (SIP) 統一資源識別項 (URI) 撥號對應表。 如果您選擇使用 Exchange 管理主控台，請建立新的撥號對應表，安全性設定 ** (偏好的) **。
    
    <div>
    

    > [!WARNING]  
    > 如果您將安全性設定值設定為 <STRONG>Sip 安全</STRONG> ，只需要加密 sip 流量（先前建議使用），請注意，如果前端集區已設定為需要加密，則此撥號對應表上的此安全性設定是不夠的，這表示集區要求對 SIP 和 RTP 流量進行加密。 當撥號對應表與集區安全性設定不相容時，前端集區中的所有 Exchange UM 呼叫將會失敗，並導致錯誤，指出您具有「不相容的安全性設定」。

    
    </div>
    
    如果您使用 Exchange 管理命令介面，請輸入：
    ```powershell
     New-UMDialPlan -Name <dial plan name> -UriType "SipName" -VoipSecurity <SIPSecured|Unsecured|Secured> -NumberOfDigitsInExtension <number of digits> -AccessTelephoneNumbers <access number in E.164 format>
    ```
    如需詳細資訊，請參閱：
    
      - 如需 Office 通訊伺服器2007，請參閱《如何建立整合通訊 SIP URI 撥號對應表》 [https://go.microsoft.com/fwlink/p/?LinkId=268632](https://go.microsoft.com/fwlink/p/?linkid=268632) 和「New-UMDialplan： Exchange 2007 Help」 at [https://go.microsoft.com/fwlink/p/?LinkId=268666](https://go.microsoft.com/fwlink/p/?linkid=268666) 。
    
      - 若為 Exchange 2010，請參閱 at [https://go.microsoft.com/fwlink/p/?LinkId=268674](https://go.microsoft.com/fwlink/p/?linkid=268674) 和「New-UMDialplan： Exchange 2010 Help "at 中的「建立 UM 撥號對應表」 [https://go.microsoft.com/fwlink/p/?LinkId=268680](https://go.microsoft.com/fwlink/p/?linkid=268680) 。
    
      - 若為 Exchange 2013，請參閱的「整合通訊」 [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579) 。
    
    <div>
    

    > [!NOTE]  
    > 您是否選取 <STRONG>SIPSecured</STRONG> 或安全的安全性層級 <STRONG>，取決於</STRONG> 是否要啟用或停用 (SRTP) 的安全即時傳輸通訊協定，以進行媒體加密。 對於 Lync Server 2010 與 Exchange UM 的整合，這應該對應至 Lync Server media 設定中的加密層級。 您可以執行 <STRONG>Get-CsMediaConfiguration</STRONG> Cmdlet 來查看 Lync Server 媒體設定。 如需詳細資訊，請參閱 Lync Server 管理命令介面檔中的 Get-CsMediaConfiguration。<BR>如需選擇適當 VoIP 安全性設定的詳細資訊，請參閱 <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">整合內部部署整合通訊和 Lync Server 2013 的部署程式</A>。

    
    </div>

2.  執行下列 Cmdlet，以取得每個 UM 撥號對應表的完整功能變數名稱 (FQDN) ：
    
    ```powershell
    (Get-UMDialPlan <dialplanname>).PhoneContext  
    ```
    
    如需詳細資訊，請參閱：
    
      - 針對 Exchange 2007，請參閱《 Get-UMDialplan： Exchange 2007 Help "at [https://go.microsoft.com/fwlink/p/?LinkId=268678](https://go.microsoft.com/fwlink/p/?linkid=268678) 。
    
      - 針對 Exchange 2010，請參閱《 Get-UMDialplan： Exchange 2010 Help "at [https://go.microsoft.com/fwlink/p/?LinkId=268679](https://go.microsoft.com/fwlink/p/?linkid=268679) 。
    
      - 若為 Exchange 2013，請參閱的「整合通訊」 [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579) 。

3.  記錄每個 UM 撥號對應表的撥號對應表名稱。 視 Exchange 伺服器的版本而定，您可能需要將每個撥號對應表名稱的 FQDN 當做每個 UM 撥號對應表對應的 Lync Server 撥號對應表的名稱，以便撥號對應表名稱相符。
    
    <div>
    

    > [!NOTE]  
    > 只有當 UM 撥號對應表在 exchange 2010 SP1 <EM>之前</EM> 的 exchange 版本上執行時，Lync Server 撥號對應表名稱才必須符合 um 撥號對應表名稱。

    
    </div>

4.  將撥號對應表新增至執行 Exchange UM 的伺服器，如下所示：
    
      - 如果您選擇使用 Exchange 管理主控台，您可以從伺服器的屬性工作表中新增撥號對應表。 如需詳細指示，請參閱 Exchange Server 產品檔。
        
        如需 Exchange 2007，請參閱如何將整合通訊伺服器新增至撥號對應表 [https://go.microsoft.com/fwlink/p/?LinkId=268681](https://go.microsoft.com/fwlink/p/?linkid=268681) 。
        
        針對 Exchange 2010，請參閱「查看或設定 UM 伺服器的屬性」 [https://go.microsoft.com/fwlink/p/?LinkId=268682](https://go.microsoft.com/fwlink/p/?linkid=268682) 。
        
        若為 Exchange 2013，請參閱的「整合通訊」 [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579) 。
    
      - 如果您使用 Exchange 管理命令介面，請針對每個 Exchange UM 伺服器執行下列命令：
        ```powershell
        $ums=get-umserver; 
        $dp=get-umdialplan -id <name of dial-plan created in step 1>; 
        $ums[0].DialPlans +=$dp.Identity; 
        set-umservice -instance $ums[0]
        ```
    <div>
    

    > [!NOTE]  
    > 在執行下列步驟之前，請確定所有的 Enterprise Voice 使用者皆已設定 Exchange Server 信箱。<BR>若為 Exchange 2007，請參閱 Exchange Server 2007 TechNet 程式庫，網址為 <A href="https://go.microsoft.com/fwlink/p/?linkid=268685">https://go.microsoft.com/fwlink/p/?LinkId=268685</A> 。<BR>若為 Exchange 2010，請參閱 Exchange Server 2010 TechNet 程式庫，網址為 <A href="https://go.microsoft.com/fwlink/p/?linkid=268686">https://go.microsoft.com/fwlink/p/?LinkId=268686</A> 。<BR>為您在步驟1中建立的每個撥號對應表指定信箱原則時，請選取 [預設原則] 或您建立的一個。

    
    </div>

5.  流覽至 [ \<Exchange installation directory\> \\ 腳本]，然後如果 Exchange 部署在單一樹系中，請輸入：
    ```console
    exchucutil.ps1
    ```
    或者，如果 Exchange 部署在多個樹系中，請輸入：
    ```console
    exchucutil.ps1 -Forest:"<forest FQDN>"
    ```
    其中，樹系 FQDN 會指定要在其中部署 Lync Server 的樹系。
    
    如果您有一個或多個與多個 IP 閘道相關聯的 UM 撥號對應表，請繼續進行步驟6。 如果您的撥號對應表彼此只與單一 IP 閘道相關聯，請跳過步驟6。
    
    <div>
    

    > [!IMPORTANT]  
    > 請務必在執行 exchucutil.ps1 之後<EM></EM>，重新啟動 <STRONG>[Lync Server 前端]</STRONG> 服務 (rtcsrv.exe)。 否則，Lync Server 將不會在拓撲中偵測到整合通訊。

    
    </div>

6.  使用 Exchange 管理命令介面或 Exchange 管理主控台，針對所有與您的撥號對應表相關聯的 IP 閘道，停用撥出電話。
    
    <div>
    

    > [!NOTE]  
    > 您必須執行此步驟，才能確保執行 Exchange Server 整合通訊的伺服器撥出電話給外部使用者 (例如，在電話上播放案例) 會以可靠的方式流覽公司防火牆。

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > 當您選取允許撥出電話的 UM IP 閘道時，請選擇一種可能處理最多流量的 UM IP 閘道。 不允許透過連接至 Lync Server Director 集區的 IP 閘道來進行傳出流量。 此外，請避免在另一個中央網站或分支網站上的集區。 您可以使用下列任何一種方法來封鎖撥出的來電，使其無法透過 IP 閘道傳遞：

    
    </div>
    
      - 如果您使用 Exchange 管理命令介面，請執行下列命令來停用每個 IP 閘道：
        ```powershell
        Set-UMIPGateway <gatewayname> -OutcallsAllowed $false
        ```
        針對 Exchange 2007，請參閱《 Set-UMIPGateway： Exchange 2007 Help "at [https://go.microsoft.com/fwlink/p/?LinkId=268687](https://go.microsoft.com/fwlink/p/?linkid=268687) 。
        
        針對 Exchange 2010，請參閱《 Set-UMIPGateway： Exchange 2010 Help "at [https://go.microsoft.com/fwlink/p/?LinkId=268688](https://go.microsoft.com/fwlink/p/?linkid=268688) 。
    
      - 如果您使用 Exchange 管理主控台，請清除 [ **允許透過此 IP 閘道的撥出電話** ] 核取方塊。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果您的 UM SIP URI 撥號對應表只與單一 IP 閘道相關聯，請勿禁止透過此閘道撥出電話。

    
    </div>

7.  建立每個 Lync Server 撥號對應表的 UM 自動語音應答。
    
    <div>
    

    > [!IMPORTANT]  
    > 請勿在自動語音應答名稱中包含任何空格。

    
    </div>
    
    ```powershell
    New-umautoattendant -name <auto attendant name> -umdialplan < name of dial plan created in step 1> -PilotIdentifierList <auto attendant phone number in E.164 format> -SpeechEnabled $true -Status Enabled
    ```
    如需詳細資訊，請參閱：
    
      - 針對 Exchange 2007，請參閱《 New-UMAutoAttendant： Exchange 2007 Help "at [https://go.microsoft.com/fwlink/p/?LinkId=268689](https://go.microsoft.com/fwlink/p/?linkid=268689) 。
    
      - 針對 Exchange 2010，請參閱《 New-UMAutoAttendant： Exchange 2010 Help "at [https://go.microsoft.com/fwlink/p/?LinkId=268690](https://go.microsoft.com/fwlink/p/?linkid=268690) 。
    
    在您為企業語音啟用 Lync Server 使用者並知道其 SIP URIs 後，每個使用者都應該執行下列步驟。

8.  建立 Exchange UM 使用者 (每個使用者都應該設定 Exchange 信箱) 與 UM 撥號對應表，並為每位使用者建立 SIP URI。
    
    <div>
    

    > [!NOTE]  
    > 下列範例中的 <STRONG>SIPResourceIdentifier</STRONG> 必須是 Lync Server 使用者的 SIP 位址。

    
    </div>
    
    ```powershell
    enable-ummailbox -id <user name> -ummailboxpolicy <name of the mailbox policy for the dial plan created in step 1> -Extensions <extension> -SIPResourceIdentifier "<user name>@<full domain name>" -PIN <user pin>
    ```
    如需詳細資訊，請參閱：
    
      - 針對 Exchange 2007，請參閱《 Enable-UMMailbox： Exchange 2007 Help "at [https://go.microsoft.com/fwlink/p/?LinkId=268691](https://go.microsoft.com/fwlink/p/?linkid=268691) 。
    
      - 針對 Exchange 2010，請參閱《 Enable-UMMailbox： Exchange 2010 Help "at [https://go.microsoft.com/fwlink/p/?LinkId=268692](https://go.microsoft.com/fwlink/p/?linkid=268692) 。

</div>

</div>

<span> </span>

</div>

</div>

</div>


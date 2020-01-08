---
title: Lync Server 2013：在 Microsoft Exchange 上設定整合通訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Unified Messaging on Microsoft Exchange
ms:assetid: 07547968-c59b-4dde-ace4-9fd286933759
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398129(v=OCS.15)
ms:contentKeyID: 48183311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c4a97a97d96f91b0433c65b7eb3e352dcf47c7d5
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40977624"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-unified-messaging-on-microsoft-exchange-for-lync-server-2013"></a>在 Microsoft Exchange for Lync Server 2013 中設定整合通訊

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-24_

本主題描述如何在 Microsoft Exchange Server 上設定 Exchange 整合通訊（UM），以搭配企業語音使用。

<div>


> [!NOTE]  
> 本主題中的 Cmdlet 範例提供 Exchange 2007 版 Exchange 管理命令介面的語法。 如果您執行的是 Exchange 2010 或 Exchange 2013，請參閱參考的相關檔。



</div>

<div>

## <a name="to-configure-a-server-running-exchange-server-um"></a>若要設定執行 Exchange Server UM 的伺服器

1.  針對您的每個企業語音位置設定檔，建立 UM 會話初始通訊協定（SIP）的統一資源識別項（URI）撥號計畫。 如果您選擇使用 Exchange 管理主控台，請建立一個安全設定為安全的新撥號方案 **（喜好）**。
    
    <div>
    

    > [!WARNING]  
    > 如果將 [安全設定] 值設定為 [ <STRONG>Sip 安全</STRONG>]，且只需要 sip 流量加密（如前所述），請注意，如果將前端池設定為需要加密，則撥號方案的此安全性設定就不足，這表示該池需要對 SIP 與 RTP 流量進行加密。 當撥號方案和池安全性設定不相容時，從前端池呼叫 Exchange UM 的所有呼叫都會失敗，並產生錯誤，指出您有「不相容的安全性設定」。

    
    </div>
    
    如果您使用 Exchange 管理命令介面，請輸入：
    ```powershell
     New-UMDialPlan -Name <dial plan name> -UriType "SipName" -VoipSecurity <SIPSecured|Unsecured|Secured> -NumberOfDigitsInExtension <number of digits> -AccessTelephoneNumbers <access number in E.164 format>
    ```
    如需詳細資訊，請參閱：
    
      - 若為 Office 通訊伺服器2007，請參閱「如何建立整合通訊 SIP URI 撥號方案」 [http://go.microsoft.com/fwlink/p/?LinkId=268632](http://go.microsoft.com/fwlink/p/?linkid=268632)和「新-UMDialplan： Exchange 2007 說明」。 [http://go.microsoft.com/fwlink/p/?LinkId=268666](http://go.microsoft.com/fwlink/p/?linkid=268666)
    
      - 若為 Exchange 2010，請參閱「建立 UM 撥號方案」 [http://go.microsoft.com/fwlink/p/?LinkId=268674](http://go.microsoft.com/fwlink/p/?linkid=268674)和「新-UMDialplan： Exchange 2010 說明」 [http://go.microsoft.com/fwlink/p/?LinkId=268680](http://go.microsoft.com/fwlink/p/?linkid=268680)。
    
      - 如需 Exchange 2013，請參閱的「整合[http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)通訊」。
    
    <div>
    

    > [!NOTE]  
    > 您是否選取 [ <STRONG>SIPSecured</STRONG> ] 或 [安全層級] <STRONG>，取決於</STRONG>是否已啟動或停用安全即時傳輸通訊協定（SRTP）以供媒體加密使用。 針對與 Exchange UM 整合的 Lync Server 2010，這應該會對應到 Lync Server 媒體設定中的加密等級。 您可以透過執行<STRONG>CsMediaConfiguration</STRONG> Cmdlet 來查看 Lync Server 媒體設定。 如需詳細資訊，請參閱 Lync Server 管理命令介面檔中的 CsMediaConfiguration。<BR>如需有關選取適當的 VoIP 安全性設定的詳細資訊，請參閱<A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">整合內部部署整合訊息和 Lync Server 2013 的部署程式</A>。

    
    </div>

2.  執行下列 Cmdlet 以取得每個 UM 撥號方案的完整功能變數名稱（FQDN）：
    
    ```powershell
    (Get-UMDialPlan <dialplanname>).PhoneContext  
    ```
    
    如需詳細資訊，請參閱：
    
      - 若為 Exchange 2007，請參閱 "UMDialplan： Exchange 2007 說明" [http://go.microsoft.com/fwlink/p/?LinkId=268678](http://go.microsoft.com/fwlink/p/?linkid=268678)。
    
      - 若為 Exchange 2010，請參閱 "UMDialplan： Exchange 2010 說明" [http://go.microsoft.com/fwlink/p/?LinkId=268679](http://go.microsoft.com/fwlink/p/?linkid=268679)。
    
      - 如需 Exchange 2013，請參閱的「整合[http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)通訊」。

3.  錄製每個 UM 撥號方案的撥號方案名稱。 根據您的 Exchange Server 版本而定，您可能需要在每個 UM 撥號方案對應的 Lync Server 撥號方案名稱之後，再使用每個撥號方案名稱的 FQDN，使撥號計畫名稱相符。
    
    <div>
    

    > [!NOTE]  
    > 如果 UM 撥號方案是在 Exchange 2010 SP1<EM>之前</EM>的 Exchange 版本上執行，則 Lync Server 撥號方案名稱必須符合 um 撥號方案名稱。

    
    </div>

4.  將撥號方案新增至執行 Exchange UM 的伺服器，如下所示：
    
      - 如果您選擇使用 Exchange 管理主控台，您可以從伺服器的屬性工作表中新增撥號方案。 如需特定指示，請參閱 Exchange Server 產品檔。
        
        針對 Exchange 2007，請參閱如何將整合通訊伺服器新增至撥號方案」 [http://go.microsoft.com/fwlink/p/?LinkId=268681](http://go.microsoft.com/fwlink/p/?linkid=268681)。
        
        若為 Exchange 2010，請參閱「查看或設定 UM 伺服器的屬性」 [http://go.microsoft.com/fwlink/p/?LinkId=268682](http://go.microsoft.com/fwlink/p/?linkid=268682)。
        
        如需 Exchange 2013，請參閱的「整合[http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)通訊」。
    
      - 如果您使用 Exchange 管理命令介面，請針對您的每個 Exchange UM 伺服器執行下列動作：
        ```powershell
        $ums=get-umserver; 
        $dp=get-umdialplan -id <name of dial-plan created in step 1>; 
        $ums[0].DialPlans +=$dp.Identity; 
        set-umservice -instance $ums[0]
        ```
    <div>
    

    > [!NOTE]  
    > 在執行下列步驟之前，請確認所有企業語音使用者都已設定 Exchange 伺服器信箱。<BR>若為 Exchange 2007，請參閱 Exchange Server 2007 TechNet 文檔<A href="http://go.microsoft.com/fwlink/p/?linkid=268685">http://go.microsoft.com/fwlink/p/?LinkId=268685</A>庫。<BR>若為 Exchange 2010，請參閱 Exchange Server 2010 TechNet 文檔<A href="http://go.microsoft.com/fwlink/p/?linkid=268686">http://go.microsoft.com/fwlink/p/?LinkId=268686</A>庫。<BR>針對您在步驟1中建立的每個撥號方案指定信箱原則時，請選取您已建立的預設原則。

    
    </div>

5.  流覽至\<exchange 安裝目錄\>\\腳本，然後，如果 Exchange 是在單一目錄林中部署，請輸入：
    ```console
    exchucutil.ps1
    ```
    或者，如果 Exchange 是部署在多個目錄林中，請輸入：
    ```console
    exchucutil.ps1 -Forest:"<forest FQDN>"
    ```
    其中，目錄林 FQDN 會指定要在其中部署 Lync Server 的林。
    
    如果您有一個或多個與多個 IP 閘道相關聯的 UM 撥號方案，請繼續執行步驟6。 如果您的撥號方案只與單一 IP 閘道相關聯，請跳過步驟6。
    
    <div>
    

    > [!IMPORTANT]  
    > 執行 exchucutil<EM>後</EM>，請務必重新開機<STRONG>Lync Server 前端</STRONG>服務（rtcsrv）。 否則，Lync Server 將不會在拓撲中偵測到統一訊息。

    
    </div>

6.  使用 Exchange 管理命令介面或 Exchange 管理主控台，除了其中一個與您的撥號方案相關聯的 IP 閘道之外，停用出站通話。
    
    <div>
    

    > [!NOTE]  
    > 您必須執行這個步驟，以確保執行 Exchange Server 的傳出通話與外部使用者（例如，與電話撥打電話案例一樣）可靠地穿越企業防火牆。

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > 選取要允許撥出電話的 UM IP 閘道時，請選擇可能會處理最大交通的通訊。 不要透過連接至 Lync Server 主管池的 IP 閘道來允許傳出流量。 此外，還要避免在另一個中央網站或分支網站中使用池。 您可以使用下列其中一種方法來封鎖撥出的呼叫，讓它透過 IP 閘道傳遞：

    
    </div>
    
      - 如果您使用 Exchange 管理命令介面，請執行下列命令以停用每個 IP 閘道：
        ```powershell
        Set-UMIPGateway <gatewayname> -OutcallsAllowed $false
        ```
        若為 Exchange 2007，請參閱 "UMIPGateway： Exchange 2007 說明" [http://go.microsoft.com/fwlink/p/?LinkId=268687](http://go.microsoft.com/fwlink/p/?linkid=268687)。
        
        若為 Exchange 2010，請參閱 "UMIPGateway： Exchange 2010 說明" [http://go.microsoft.com/fwlink/p/?LinkId=268688](http://go.microsoft.com/fwlink/p/?linkid=268688)。
    
      - 如果您使用 Exchange 管理主控台，請清除 [**允許透過此 IP 閘道撥出電話**] 核取方塊。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果您的 UM SIP URI 撥號方案只與單一 IP 閘道相關聯，請不要透過此閘道禁止撥出通話。

    
    </div>

7.  針對每個 Lync Server 撥號方案建立 UM 自動助理。
    
    <div>
    

    > [!IMPORTANT]  
    > 不要在自動語音應答的名稱中包含任何空格。

    
    </div>
    
    ```powershell
    New-umautoattendant -name <auto attendant name> -umdialplan < name of dial plan created in step 1> -PilotIdentifierList <auto attendant phone number in E.164 format> -SpeechEnabled $true -Status Enabled
    ```
    如需詳細資訊，請參閱：
    
      - 若為 Exchange 2007，請參閱「新-UMAutoAttendant： Exchange 2007 說明[http://go.microsoft.com/fwlink/p/?LinkId=268689](http://go.microsoft.com/fwlink/p/?linkid=268689)」。
    
      - 若為 Exchange 2010，請參閱「新-UMAutoAttendant： Exchange 2010 說明[http://go.microsoft.com/fwlink/p/?LinkId=268690](http://go.microsoft.com/fwlink/p/?linkid=268690)」。
    
    當您已為企業語音啟用 Lync Server 使用者並知道其 SIP Uri 之後，就應該針對每位使用者執行下列步驟。

8.  將 Exchange UM 使用者（每位使用者都應該使用 Exchange 信箱設定）與 UM 撥號方案建立關聯，並為每位使用者建立 SIP URI。
    
    <div>
    

    > [!NOTE]  
    > 下列範例中的<STRONG>SIPResourceIdentifier</STRONG>必須是 Lync Server 使用者的 SIP 位址。

    
    </div>
    
    ```powershell
    enable-ummailbox -id <user name> -ummailboxpolicy <name of the mailbox policy for the dial plan created in step 1> -Extensions <extension> -SIPResourceIdentifier "<user name>@<full domain name>" -PIN <user pin>
    ```
    如需詳細資訊，請參閱：
    
      - 若為 Exchange 2007，請參閱 "Enable-UMMailbox： Exchange 2007 說明[http://go.microsoft.com/fwlink/p/?LinkId=268691](http://go.microsoft.com/fwlink/p/?linkid=268691)"。
    
      - 若為 Exchange 2010，請參閱 "Enable-UMMailbox： Exchange 2010 說明[http://go.microsoft.com/fwlink/p/?LinkId=268692](http://go.microsoft.com/fwlink/p/?linkid=268692)"。

</div>

</div>

<span> </span>

</div>

</div>

</div>


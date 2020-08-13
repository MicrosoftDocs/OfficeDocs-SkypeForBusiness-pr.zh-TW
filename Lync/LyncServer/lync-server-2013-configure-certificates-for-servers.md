---
title: Lync Server 2013：設定伺服器的憑證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates for servers
ms:assetid: e12e59b5-a146-4859-86ec-cabfc198c7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398995(v=OCS.15)
ms:contentKeyID: 48185531
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3556c9147ddf2769e6a403de9e31edf31129d796
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205059"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-servers-in-lync-server-2013"></a>在 Lync Server 2013 中設定伺服器的憑證

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-17_

若要順利完成此程式，您應該以 RTCUniversalServerAdmins 群組成員的使用者身分登入，或是委派正確的許可權。 如需有關委派許可權的詳細資訊，請參閱[在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。 根據您的組織以及對要求憑證的需求，您可能需要其他群組成員資格。 請向負責管理公開金鑰基礎結構 (PKI) 憑證授權單位 (CA) 的部門洽詢相關資訊。

<div>


> [!NOTE]  
> Lync Server 2013 包含對 SHA-2 套件的支援 (SHA-2 對執行 Windows 7、Windows Server 512 R2、Windows Server 2008、windows Vista 或 Windows XP 作業系統的用戶端，除了 Lync Phone Edition 之外，針對來自執行 Windows 7、Windows Server 2008 R2、windows Server、windows Vista 或 Windows XP 作業系統的用戶端，使用摘要雜湊及簽署演算法的摘要 384 256 224 的長度) 的 若要使用 SHA-2 套件來支援外部存取，外部憑證是由公用 CA 所發出，也可以使用相同位長度的摘要來發出憑證。



</div>

<div>


> [!WARNING]  
> 您可以選擇哪些雜湊摘要和簽署演算法取決於用戶端和將使用憑證的伺服器，以及用戶端和伺服器要與其通訊的其他電腦和裝置，也必須瞭解如何使用憑證中所用的演算法。 如需作業系統和某些用戶端應用程式中支援摘要長度的詳細資訊，請參閱 <A href="https://go.microsoft.com/fwlink/?linkid=287002">https://go.microsoft.com/fwlink/?LinkId=287002</A> 。



</div>

每個 Standard Edition server 或前端伺服器最多需要四個憑證： oAuthTokenIssuer 憑證、預設憑證、網頁內部憑證和網頁外部憑證。 不過，您可以使用適當的主體替代名稱專案以及 oAuthTokenIssuer 憑證要求並指派單一預設憑證。 如需憑證需求的詳細資訊，請參閱[Lync Server 2013 中內部伺服器的憑證需求](lync-server-2013-certificate-requirements-for-internal-servers.md)。 如需有關要求、指派及安裝 oAuthTokenIssuer 憑證的詳細資訊，請參閱[管理伺服器對伺服器驗證 (OAuth) 和夥伴應用程式的 Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)

使用下列程式可要求、指派及安裝 Standard Edition server 或前端伺服器憑證。 針對每一部前端伺服器重複此程式。

<div>


> [!IMPORTANT]  
> 下列程式說明如何從組織部署的內部 enterprise PKI 設定憑證，並以離線要求處理。 如需從公用 CA 取得憑證的詳細資訊，請參閱規劃檔中的<A href="lync-server-2013-certificate-requirements-for-internal-servers.md">Lync Server 2013 內部伺服器的憑證需求</A>。 此外，此程式也說明如何在設定前端伺服器期間要求、指派及安裝憑證。 如果您事先要求憑證，如本部署檔的 [<A href="lync-server-2013-request-certificates-in-advance-optional.md">要求憑證中 (選用 2013) </A> ] 區段所述，或是您未使用組織中部署的內部企業 PKI 來取得憑證，您必須視需要修改此程式。



</div>

<div>

## <a name="to-configure-certificates-for-a-front-end-server"></a>若要為前端伺服器設定憑證

1.  在 [Lync Server 部署嚮導] 中，按一下 [**步驟3：要求、安裝或指派憑證**] 旁邊的 [**執行**]。

2.  在 **[憑證精靈]** 頁面中，按一下 **[要求]**。

3.  在 **[憑證要求]** 頁面上，按 **[下一步]**。

4.  在 [**延遲或立即要求**] 頁面上，按一下 **[下一步]**，可接受預設**立即將要求傳送到線上憑證授權單位**單位選項。 如果您選取此選項，則必須使用具有自動線上註冊的內部 CA。 如果您選擇延遲要求的選項，系統會提示您輸入名稱和位置，以儲存憑證要求檔案。 憑證要求必須由組織內的 CA 或公用 CA 所呈現及處理。 接著，您將需要匯入憑證回應，並將它指派給適當的憑證角色。

5.  在 [**選擇憑證授權單位單位 (CA) ** ] 頁面上，選取 [**從環境中偵測到的清單選取 CA** ] 選項，然後從清單中的 Active DIRECTORY 網域服務) CA 註冊，以選取已知 (。 或者，選取 [**指定另一個憑證授權單位**單位] 選項，然後在方塊中輸入另一個 CA 的名稱，然後按 **[下一步]**。

6.  在 [**憑證授權單位單位帳戶**] 頁面上，系統會提示您輸入認證要求並處理 CA 的憑證要求。 您應該已確定使用者名稱和密碼是否需要預先要求憑證。 您的 CA 管理員會有必要的資訊，而且可能需要在此步驟中協助您。 如果您需要提供替代認證，請選取 [核取方塊]，在文字方塊中提供使用者名稱和密碼，然後按 **[下一步]**。

7.  在 [**指定替代的憑證範本**] 頁面上，若要使用預設 Web 服務器範本，請按 **[下一步]**。
    
    <div>
    

    > [!NOTE]  
    > 如果您的組織已建立用作預設網頁伺服器 CA 範本的替代範本，請選取核取方塊，然後輸入備用範本的名稱。 您將需要 CA 管理員所定義的範本名稱。

    
    </div>

8.  在 [**名稱和安全性設定**] 頁面上，指定可讓您識別憑證和用途的**易記名稱**。 如果保留空白，則會自動產生名稱。 設定機碼的**位長度**，或接受預設值2048位。 選取 [將**憑證的私密金鑰標記為可匯出**] 如果您決定要將憑證和私密金鑰移動或複製到其他系統，請按一下 [**下一步]**。
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 具有可匯出私密金鑰的最低需求。 其中一個地方是在集區中的 Edge Server 上，媒體轉送驗證服務使用憑證的副本，而不是集區中每個實例的個別憑證。

    
    </div>

9.  在 [**組織資訊**] 頁面上，選擇提供組織資訊，然後按 **[下一步]**。

10. 在 [**地理資訊**] 頁面上，選擇提供地理資訊，然後按 **[下一步]**。

11. 在 [**主體名稱/主體替代名稱**] 頁面上，複查將要新增的主體替代名稱，然後按 **[下一步]**。

12. 在 [ **SIP 網域設定**] 頁面上，選取 [ **sip 網域**]，然後按 **[下一步]**。

13. 在 [**設定其他主體替代名稱**] 頁面上，新增任何其他必要的主體別名，包括未來其他 SIP 網域可能需要的主體替代名稱，然後按 **[下一步]**。

14. 在 [**憑證要求摘要**] 頁面上，複查摘要中的資訊。 如果資訊正確，按 **[下一步]**。 如果您需要更正或修改設定，請按一下 [**回到**正確的頁面]，以進行更正或修改。

15. 在 **[執行命令]** 頁面上，按 **[下一步]**。

16. 在 [**線上憑證要求狀態**] 頁面上，複查傳回的資訊。 您應注意，已簽發憑證並將其安裝至本機憑證儲存區。 若報告為已簽發並已安裝，但無效，請確定伺服器的根信任 CA 存放區中已安裝 CA 的根憑證。 請參閱您的 CA 檔，瞭解如何取得信任的根 CA 憑證。 如果您需要查看已檢索的憑證，請按一下 [**查看憑證詳細資料**]。 依預設，會檢查**指派憑證至 Lync Server 憑證使用**情況的核取方塊。 若要手動指派憑證，請清除核取方塊，然後按一下 **[完成]**。

17. 如果您已清除 [**將憑證指派給舊版的 Lync Server 憑證使用**情況] 核取方塊，將會出現 [**憑證指派**] 頁面。 按 [下一步]****。

18. 在 [**憑證存放區**] 頁面上，選取您要求的憑證。 如果您想要查看憑證，請按一下 [**查看憑證詳細資料**]，然後按 **[下一步]** 繼續。
    
    <div>
    

    > [!NOTE]  
    > 如果 [<STRONG>線上憑證要求狀態</STRONG>] 頁面報告憑證有問題，例如憑證無效，則查看實際憑證可以協助解決問題。 兩個可能造成憑證無法使用的特定問題，都是先前提及的遺失信任的根 CA 憑證，以及與憑證相關聯的遺失私密金鑰。 請參閱 CA 檔，以解決這兩個問題。

    
    </div>

19. 在 [**憑證指派摘要**] 頁面上，複查所呈現的資訊，確定這是應該指派的憑證，然後按 **[下一步]**。

20. 在 [**執行命令**] 頁面上，複查命令的輸出。 如果您想要複查指派程式，或是發出錯誤或警告，請按一下 [ **View Log** ]。 完成審閱後，請按一下 **[完成]**。

21. 在 [**憑證] 嚮導**頁面上，確認憑證的**狀態**為「已指派」，然後按一下 [**關閉**]。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 的憑證基礎結構需求](lync-server-2013-certificate-infrastructure-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


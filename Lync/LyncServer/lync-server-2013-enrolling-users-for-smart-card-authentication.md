---
title: Lync Server 2013：針對智慧卡驗證註冊使用者
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enrolling users for smart card authentication
ms:assetid: a6445a83-a94b-423f-ba2a-12b5f84c5d75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308570(v=OCS.15)
ms:contentKeyID: 54973691
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cfbfcd73aba4079d74074adcd2710b8a2d45aeba
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526770"
---
# <a name="enrolling-users-for-smart-card-authentication-in-lync-server-2013"></a>在 Lync Server 2013 中登記智慧卡驗證的使用者

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-07-03_

有兩種方法可供您登記智慧卡驗證的使用者。 較簡單的方法是讓使用者直接註冊使用 web 註冊的智慧卡驗證，而更複雜的方法則是使用註冊代理程式。 本主題著重于智慧卡憑證的自我註冊。

如需以登錄代理程式的身分登記使用者的詳細資訊，請參閱在上註冊憑證的其他使用者 [https://go.microsoft.com/fwlink/p/?LinkID=313367](https://go.microsoft.com/fwlink/p/?linkid=313367) 。

<div>

## <a name="to-enroll-users-for-smart-card-authentication"></a>註冊使用者的智慧卡驗證

1.  使用啟用 Lync 功能之使用者的認證登入 Windows 8 工作站。

2.  啟動 Internet Explorer。

3.  流覽至 [ **憑證授權單位 Web 登記** ] 頁面 (https://MyCA.contoso.com/certsrv) 例如，
    
    <div>
    

    > [!NOTE]  
    > 如果您使用的是 Internet Explorer 10，您可能需要在相容性模式中查看此網站。

    
    </div>

4.  在 [ **歡迎** ] 頁面上，選取 [ **要求憑證**]。

5.  接下來，選取 [ **高級要求**]。

6.  選取 [ **建立並提交此 CA 的要求**]。

7.  在 [**憑證範本**] 區段中選取 [**智慧卡使用者**]，並以下列值完成「高級憑證要求」：
    
      - **主要選項** 確認他的下列設定：
        
          - 選取 [ **建立新的按鍵集** ] 選項按鈕
        
          - 若為**CSP**，請選取 [ **Microsoft 基本智慧卡加密提供者**]
        
          - 如需 **主要用法**，請選取 [ **Exchange** (這是唯一可用的選項) 。
        
          - 若為 **金鑰大小**，請輸入 **2048**
        
          - 確認已選取 [ **自動機碼容器名稱** ]
        
          - 請不要選取其他方塊。
    
      - 在 [ **其他選項** ] 下，確認下列值：
        
          - 若為 **要求格式** ，請選取 **CMC**。
        
          - 若為 **雜湊演算法** ，請選取 **sha1**。
        
          - 若為 **易記名稱** ，請輸入 **Smardcard 憑證**。

8.  如果您使用的是實體智慧卡讀卡機，請將智慧卡插入裝置中。

9.  按一下 [ **提交** ] 提交憑證要求。

10. 出現提示時，請輸入用來建立虛擬智慧卡的 PIN 碼。
    
    <div>
    

    > [!NOTE]  
    > 預設虛擬智慧卡 PIN 碼值為 ' 12345678 '。

    
    </div>

11. 簽發憑證後，按一下 [ **安裝此憑證** ] 以完成註冊程式。
    
    <div>
    

    > [!NOTE]  
    > 如果憑證要求失敗，錯誤為「此網頁瀏覽器不支援產生憑證要求」，有三種方法可以解決問題： 
    > <OL>
    > <LI>
    > <P>在 Internet Explorer 中啟用相容性檢視</P>
    > <LI>
    > <P>在 Internet Explorer 中啟用 [開啟內部網路設定] 選項</P>
    > <LI>
    > <P>選取 [Internet Explorer 選項] 功能表中 [安全性] 索引標籤底下的 [將所有區域重設為預設層級] 設定。</P></LI></OL>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


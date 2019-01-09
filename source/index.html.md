---
title: LATELY API Reference V3.21

toc_footers:
  - <a href='http://pravs.co.kr' target='_blank'>PRAVS</a>
  - <a href='http://lately.co.kr' target='_blank'>LATELY</a>

search: true
---

# History

버전 | 개정일자 | 내용
---- | -------- | ----
1.0 | 2012-02-06 | 최초작성
1.1 | 2012-04-26 | 전체주문내역, 상품승인상태확인 추가
2.0 | 2012-12-07 | 레퍼런스 수정 및 발송 지연 처리 추가
2.1 | 2013-03-04 | 판매거부 (발송전 주문취소) 처리 추가
 | 2013-03-11 | 상품 이미지 업데이트(재등록)여부 필드 추가 (2-5. 상품등록/수정)
 | 2013-05-06 | 상품 이미지 다중 등록 (2-5. 상품등록/수정)
 | 2013-08-21 | 타임세일기능 추가 (2-5. 상품등록/수정)
 | 2013-12-18 | 주문리스트 조회 조건 변경 및 결제일 추가
2.2 | 2014-04-09 | 상품등록 – 상품정보고시 4개 항목 추가.<br>주문리스트에 묶음배송코드(DeliveryPackge) 추가.<br>구매확정리스트 조회
3.00 | 2017-02-08 | API가이드 전면 개편
3.01 | 2017-04-17 | 전상품 고유번호 조회 API 추가, 정보고시항목추가(인증서번호), 기타 마이너 업데이트
3.02 | 2017-04-20 | KC인증정보추가, 입금확인 상태의 주문도 발송처리(OrderInvoice) 가능하도록 수정
3.03 | 2017-05-23 | 부분취소 관련 필드 추가, 정보고시그룹 추가, 배송비유형코드 필수항목 표기 오류 수정, 기타 마이너 업데이트
3.04 | 2017-07-24 | 전체카테고리조회 추가, 상품등록/수정 API 수정, 주문/취소리스트 API 수정 등. 기타 마이너 업데이트
3.1 | 2018-03-23 | 옵션관련 API추가
3.11 | 2018-04-19 | 주문관련 API 가이드 보완/수정, 기타 마이너 업데이트
3.2 | 2018-11-29 | 상품정보고시 그룹 추가
3.21 | 2019-01-09 | 주문리스트 검색 조건 추가, 상품정보조회 API 추가

# ChangeLog

## v3.21 / 2019-01-09
- 주문리스트(OrderInfo) vmode를 null로 설정 시 입금확인 주문만 가져오도록 수정
- 주문리스트(OrderInfo) vmode를 pre로 설정 시 배송준비중 주문만 가져도오록 조건 추가
- 주문리스트(OrderInfo) 주문번호(OrderID) 검색조건 추가
- 주문리스트(OrderInfo) 주문상세번호(OrderItemID) 검색조건 추가
- 2-6-2. 상품 정보 조회(GetGoodsInfo) API 추가
- 오타 및 버그 수정

## v3.2 / 2018-11-29
- 상품정보고시 그룹추가
- g16 영상가전
- g17 계절가전
- g18 사무용기기
- g19 광학기기
- g20 소형전자
- g21 내비게이션
- g22 자동차용품
- g23 의료기기

## v3.11 / 2018-04-19
- 주문관련 설명이 실제 API스펙과 다른부분 수정.
- 오타 및 버그 수정

## v3.1 / 2018-03-23
- 옵션관련 API추가 (옵션조회, 상품전체옵션조회, 옵션등록, 옵션수정, 옵션삭제)
- 옵션 등록수정시 옵션API 사용 권장. 기존방식도 사용가능(상품 등록/수정 API, UnitInfo)
- 주문리스트에서 주문옵션명외에 등록옵션명 필드 추가
- (중요) 옵션API를 사용할 경우 반드시 상품등록(Goods) API에서 OptIf 값을 "Y"로 전송

## v3.04 / 2017-07-24
- 전체카테고리 목록조회(GetAllCategory) API 추가
- 상품등록/수정(Goods) API에 옵션가(OptPrice) 필드 추가, 옵션가 사용할 경우 OptPrice을 1로 설정
- 전체택배사리스트조회 GetAllDelivery, GetAllDeliveryInfo 동일하게 호출가능
- 주문리스트에 DeliDueDt 필드 삭제 (사용안함)
- 주문/취소리스트 호출시 시간 단위까지 설정 가능하도록 수정
- 주문취소리스트 OrderClaim, OrderClame 동일하게 호출 가능
- 주문취소리스트 API에 ClaimCode, 원주문옵션(교환건일경우, OriOpt) 필드 추가
- 코드 5-8 취소/교환/반품 관련 코드표 추가
- 오타 및 버그 수정

## v3.03 / 2017-05-23
- 주문리스트 API(OrderInfo)에 부분취소된 수량 있을경우 취소수량(CancelQty) 필드에 표시
- 주문취소/반품/교환리스트 API(OrderClaim)에 부분 취소/반품/교환일 경우 원주문상세번호(OrderOldID) 필드에 표시
- 정보고시 그룹 g14 식품(농수산물), g15 건강기능식품 추가
- 배송비유형코드(DeliveryChange) "기본정책"일 경우 Delfee항목 공백으로 설정가능.
- 식품관련 카테고리 추가. 관련 API(GetCategory)에서 확인가능.
- 택배사코드 추가 101(자체배송), 102(기타). 관련 API(GetDelivery, GetAllDelivery)에서 확인가능.

## v3.02 / 2017-04-20
- 상품등록수정(Goods) API에 KC 안전인증 정보입력 항목 추가
- KC 안전인증 정보유형 및 유형에 따른 상세내용(인증번호 등) 입력여부. 부록 6-3 참고
- 입금확인 상태의 주문도 발송처리(OrderInvoice) 가능하도록 수정

## v3.01 / 2017-04-17
- 전상품 고유번호 조회 API추가 (GetGoodsList), 상품전송 후 통신오류등으로 Response 값을 받지 못했을때 사용
- 정보고시에 인증서번호(ItemWarranty_number, varchar(50)) 항목 추가

## v3.00 / 2017-02-08
- 기존 PDF / DOC 파일로 배포되던 API가이드는 파기하고 WEB환경으로 변경
- 법인명 변경으로 PRAVS(프라브)로 표기되던 부분을 LATELY(레이틀리)로 변경(API 전문 제외)
- (중요) 3-5 발송처리 인터페이스명 OrderConfirm > OrderInvoice로 변경
- (중요) 3-1 주문리스트, 3-6 주문취소/반품/교환리스트 API에 교환상태 필드(OrderExchange) 누락 수정
- (중요) 정보고시그룹 g8 ~ g13 추가
- 구매확정 주문 리스트(OrderBuyConfirm), 구매확정 취소 리스트(OrderConfirmClaim) API를 모든 공급사에서 사용가능하도록 수정
- 발송지연사유 코드표 추가 / 판매거부코드 코드표 추가
- 교환상태 코드표에 상태 값 추가 : 교환완료(5)
- 담당자정보 수정 / 기타 마이너 누락사항 및 오타 수정

# 1. 소개

## 1-1. 기본 메세지 구조
- 쇼핑몰 SCM 연동 API는 HTTPS Protocol을 이용해 통신하는 것을 기본 원칙으로 합니다.
- 데이터를 전송할 때는 POST 방식으로 Submit 하시고, 수행 결과값은 XML을 통해 회신합니다.
- API 수행결과가 실패인 경우 아래의 XML을 회신합니다.

`<?xml version="1.0" encoding="euc-kr" ?>`<br>
`<Pravs>`<br>
`<Header>`<br>
`   <SendLinker>API 연동업체 ID</SendLinker>`<br>
`   <SendID>공급사 ID</SendID>`<br>
`   <SendDate>요청날짜</SendDate>`<br>
`</Header>`<br>
`<Result>FAIL</Result>`<br>
` -- 아래 표 참조 -- `<br>
`</Pravs>`

사유 | 내용
---- | ----
공급사인증실패(공통) | `<Msg><![CDATA[로그인 실패]]></Msg>`
카테고리 조회 실패 | `<Msg><![CDATA[카테고리 조회 실패]]></Msg>`
브랜드 조회 실패 | `<Msg><![CDATA[브랜드 조회 실패]]></Msg>`
상품등록 실패 | `<ItemGoodCode>LATELY 상품고유번호</ItemGoodCode>`<br>`<ItemNo>업체 상품고유번호</ItemNo>`<br>`<ItemPartnerCode>상품품번</ItemPartnerCode>`<br>`<Msg><![CDATA[상품등록 실패]]></Msg>`
주문(취소)조회 실패 | `<StartDt>조회 시작일자</StartDt>`<br>`<EndDt>조회 종료일자</EndDt>`<br>`<Msg><![CDATA[주문(취소)조회 실패]]></Msg>`
발주처리 실패 | `<OrderID>주문번호</OrderID>`<br>`<OrderItemID>주문상세번호</OrderItemID>`<br>`<Msg><![CDATA[발주처리 실패]]></Msg>`
발송처리 실패 | `<OrderID>주문번호</OrderID>`<br>`<OrderItemID>주문상세번호</OrderItemID>`<br>`<Delv_Cd>택배사 코드</Delv_Cd>`<br>`<Invoice>송장번호</Invoice>`<br>`<Msg><![CDATA[발송처리 실패]]></Msg>`

## 1-2. TargetURL
- https://pravs.co.kr/shop/_OpenAPI/link.[Interface Name].php

## 1-3. API 통신 서버 등록
- 레이틀리서버로 접근하는 모든 서버IP를 레이틀리 담당자에게 전달해 주시기 바랍니다.
- 특정 IP대역대로 등록 가능합니다. 예) xxx.xxx.xxx
- 등록 되지 않은 IP로는 API 통신이 불가합니다.

## 1-4. API 연동 순서
1. 서비스 신청, 연동 서버 IP 등록
2. LinkerID 및 Test 계정 발급
3. API 개발 및 검수
4. 실사용 계정 등록
5. 서비스 시작

## 1-5. 문의처
레이틀리코리아 개발팀 양민선 과장 / yms@lately.co.kr (참조:dev@lately.co.kr) / 070-4632-1666

# 2. 상품관련 API

## 2-1-1. 카테고리 목록 조회
- Interface Name : GetCategory
- Description : 공급사별 사용 가능한 카테고리 목록을 조회합니다.

### Request Data (POST)
순번 | 필드명   | 필드설명        | 타입        | 필수 | 비고
---- | -------- | --------------- | ----------- | ---- | ----
1    | LinkerID | Link 연동 ID    | Varchar(15) | 필수 |
2    | UserID   | 공급사 아이디   | Varchar(20) | 필수 |
3    | UserPW   | 공급사 비밀번호 | Varchar(20) | 필수 |

### Response Data(XML)
순번 | 필드명        | 필드설명     | CDATA | 비고
---- | ------------- | ------------ | ----- | ----
1    | CategoryDepth | 카테고리단계 |       | 1차, 2차, 3차, 4차
2    | CategoryCd    | 카테고리코드 |       |
3    | CategoryNm    | 카테고리명   | 사용  |

## 2-1-2. 전체 카테고리 목록 조회
- Interface Name : GetAllCategory
- Description : 전체 카테고리 목록을 조회합니다.

### Request Data (POST)
순번 | 필드명   | 필드설명        | 타입        | 필수 | 비고
---- | -------- | --------------- | ----------- | ---- | ----
1    | LinkerID | Link 연동 ID    | Varchar(15) | 필수 |
2    | UserID   | 공급사 아이디   | Varchar(20) | 필수 |
3    | UserPW   | 공급사 비밀번호 | Varchar(20) | 필수 |

### Response Data(XML)
순번 | 필드명        | 필드설명     | CDATA | 비고
---- | ------------- | ------------ | ----- | ----
1    | CategoryDepth | 카테고리단계 |       | 1차, 2차, 3차, 4차
2    | CategoryCd    | 카테고리코드 |       |
3    | CategoryNm    | 카테고리명   | 사용  |

## 2-2. 브랜드 조회
- Interface Name : GetBrand
- Description : 공급사별 사용 가능한 브랜드 목록을 조회합니다.

### Request Data (POST)
순번 | 필드명   | 필드설명        | 타입        | 필수 | 비고
---- | -------- | --------------- | ----------- | ---- | ----
1    | LinkerID | Link 연동 ID    | Varchar(15) | 필수 |
2    | UserID   | 공급사 아이디   | Varchar(20) | 필수 |
3    | UserPW   | 공급사 비밀번호 | Varchar(20) | 필수 |

### Response Data(XML)
순번 | 필드명    | 필드설명   | CDATA | 비고
---- | --------- | ---------- | ----- | ----
1    | brandCode | 브랜드코드 |       |
2    | brandName | 브랜드명   | 사용  |

## 2-3. 택배사 리스트
- Interface Name : GetDelivery
- Description : 공급사별 사용 가능한 택배사 목록을 조회합니다.

### Request Data (POST)
순번 | 필드명   | 필드설명        | 타입        | 필수 | 비고
---- | -------- | --------------- | ----------- | ---- | ----
1    | LinkerID | Link 연동 ID    | Varchar(15) | 필수 |
2    | UserID   | 공급사 아이디   | Varchar(20) | 필수 |
3    | UserPW   | 공급사 비밀번호 | Varchar(20) | 필수 |

### Response Data(XML)
순번 | 필드명       | 필드설명   | CDATA | 비고
---- | ------------ | ---------- | ----- | ----
1    | DeliveryID   | 택배사코드 |       |
2    | DeliveryName | 택배사명   | 사용  |

## 2-4. 전체 택배사 리스트
- Interface Name : GetAllDelivery (+GetAllDeliveryInfo 동일)
- Description : 전체 택배사 목록을 조회합니다.

### Request Data (POST)
순번 | 필드명   | 필드설명     | 타입        | 필수 | 비고
---- | -------- | ------------ | ----------- | ---- | ----
1    | LinkerID | Link 연동 ID | Varchar(15) | 필수 |

### Response Data(XML)
순번 | 필드명       | 필드설명   | CDATA | 비고
---- | ------------ | ---------- | ----- | ----
1    | DeliveryID   | 택배사코드 |       |
2    | DeliveryName | 택배사명   | 사용  |

## 2-5. 상품등록/수정
- Interface Name : Goods
- Description : 상품 및 옵션을 등록/수정합니다.(상품정보고시 포함)

### Request Data (POST)
순번 | 필드명                     | 필드설명               | 타입                | 필수 | 비고
---- | -------------------------- | ---------------------- | ------------------- | ---- | ----
1    | LinkerID                   | Link 연동 ID           | Varchar(15)         | 필수 |
2    | UserID                     | 공급사 아이디          | Varchar(20)         | 필수 |
3    | UserPW                     | 공급사 비밀번호        | Varchar(20)         | 필수 |
4    | ItemNo                     | 상품번호               | Int(10)             | 필수 | 쇼핑몰로 보내는 업체 상품고유번호
5    | ItemPartnerCode            | 상품품번               | Int(10)             |      | 상품품번
6    | ItemCategory               | 카테고리               | Varchar(200)        | 필수 | 카테고리 코드(2개이상 등록시 세로바 &#124; 구분)<br>Ex : 001001001&#124;002001001&#124;001002003
7    | ItemBrand                  | 브랜드                 | Int(10)             | 필수 | 브랜드 코드 (2-2.브랜드조회에서 확인)
8    | ItemName                   | 상품명                 | Varchar(200)        | 필수 |
9    | ItemGoodCode               | 쇼핑몰 상품번호        | Int(10)             |      | 수정 시만 사용(등록 시 리턴 됨)
10   | Itemkeyword                | 검색어                 | Varchar(200)        |      | 콤마(,)로 구분
11   | Itemicon                   | 상품정보 아이콘        | Varchar(32)         |      | 신상,기획,추천,인기 등
12   | Launchdate                 | 제조년월               | Varchar(200)        |      |
13   | ItemMaker                  | 제조사(제조자)         | Varchar(200)        |      | 제조사 및 수입처
14   | ItemMadeIn                 | 원산지                 | Varchar(50)         |      |
15   | ItemDesc                   | 상품간단설명           | Varchar(200)        |      |
16   | ItemDescDetail             | 상품상세설명           | Text                | 필수 |
17   | ItemImage                  | 상품이미지             | text                | 필수 | 상품 대표 이미지URL 가로 500px 이상<br>(http를 포함한 전체 URL을 전송)<br>상품이미지 2개 이상 등록 시 세로구분자 "&#124;" 사용<br>(ex : http://pravs.co.kr/img/1.jpg|http://pravs.co.k r/img/2.jpg)
18   | ItemImageUpt               | 이미지업데이트         | Enum(Y,N)           |      | "Y"로 전송할 경우 상품 이미지를 무조건 업데이 트 함.
19   | ItemCount                  | 상품수량(재고)         | Int(10)             |      |
20   | TaxYn                      | 과세여부               | Char(3)             | 필수 | 001:과세,002:과세
21   | BuyPrice                   | 공급가                 | Int(10)             |      |
22   | MarginRate                 | 마진율                 | Decimal(9,2)        |      | 소수점 2자리까지
23   | SalePrice                  | 판매가                 | Int(10)             |      |
24   | ConsumerPrice              | 소비자가                   | Int(10)             |      |
25   | DeliveryChange             | 배송비 구분            | Char(3)             | 필수 | 코드 1. 배송비 유형 코드
26   | Delfee                     | 배송비                 | Int(10)             |      |
27   | Unittype                   | 옵션출력방식           | Enum(single,double) |      |
28   | UnitInfo                   | 옵션정보               | Text                |      | 부록 1. 상품옵션 전송 방법
29   | OptPrice                   | 옵션정보               | int(10)             |      | 값이 "1"일 경우 옵션가 사용
30   | Detailview                 | 상품이미지 돋보기효과  | Enum(y,n)           |      |
31   | SaleStatus                 | 판매상태               | Enum(001,004)       | 필수 | 001:판매중,004:품절
32   | StockYn                    | 재고 차감 사용여부     | Enum(001,002)       | 필수 | 001:재고량차감,002:차감안함
33   | ItemMode                   | 등록/수정              | Enum(I,M)           | 필수 | I : 등록, M : 수정
34   | ItemGoodsRequired          | 필수입력그룹코드       | Char(2)             | 필수 | 표 1-2. 상품정보 필수입력 그룹 표<br>(33 ~ 54 : 상품군별 상품정보 필수입력 항목 확인)
35   | ItemMatiere                | 제품소재               | Varchar(200)        |      |
36   | ItemColors                 | 색상                   | Varchar(200)        |      |
37   | ItemSizes                  | 치수 또는 크기         | Varchar(200)        |      |
38   | ItemKinds                  | 종류                   | Varchar(200)        |      |
39   | ItemCaution                | 취급 시 주의사항       | Text                |      | 사용시 주의 사항
40   | ItemVolume                 | 용량 또는 중량         | Varchar(200)        |      |
41   | ItemServiceLife            | 사용기한               | Varchar(200)        |      |
42   | ItemUsages                 | 사용방법               | Text                |      |
43   | ItemSpec1                  | 제품주요사양           | Text                |      |
44   | ItemSpec2                  | 제품세부사양           | Text                |      |
45   | ItemUseAge                 | 사용연령               | Varchar(200)        |      |
46   | ItemEqualModelLaunchdt     | 동일모델의 출시 년월   | Varchar(200)        |      |
47   | ItemIngredient             | 주요성분               | Varchar(200)        |      |
48   | ItemWarranty               | 품질인증여부           | Enum(Y,N)           |      | 보증서존재 여부 등
49   | ItemWarranty_number        | 보증서 인증번호        | Varchar(50)         |      |
50   | ItemWarrantyGov            | 인증기관               | Varchar(200)        |      | KC인증필 인증기관
51   | ItemQualityAssurance       | 품질보증기준           | Varchar(200)        |      |
52   | ItemAsTel                  | AS 전화번호            | Varchar(50)         | 필수 |
53   | ItemAsName                 | AS 책임자              | Varchar(50)         | 필수 |
54   | ItemNoRefund               |                        | Varchar(200)        |      | 제품 하자가 아닌 소비자의 단순 변심, 착오 구매에<br>따른 청약 철회가 불가능한 경우 그 구체적 사유와 근거
55   | ItemReturnQualityAssurance |                        | Varchar(200)        |      | 재화 등의 교환·반품·보증 조건 및 품질 보증 기준
56   | ItemCompensation           |                        | Varchar(200)        |      | 대금을 환불받기 위한 방법과 환불이  지연될 경우<br>지연에 따른 배상금을 지급받을 수 있다는 사실 및<br>배상금 지급의 구체적 조건 및 절차
57   | ItemTroubleShooting        |                        | Varchar(200)        |      | 소비자 피해 보상의 처리, 재화 등에 대한 불만 처리<br>및 소비자와 사업자 사이의 분쟁처리에 관한 사항
58   | TimeSaleUse                | 타임세일 사용여부      | Enum(0,1)           |      | 0:사용안함, 1:사용
59   | TimeSaleValidSdate         | 타임세일 시작일시      | Datetime            |      | 0000-00-00 00:00:00 (타임세일 사용시 필수)
60   | TimeSaleValidEdate         | 타임세일 종료일시      | Datetime            |      | 0000-00-00 00:00:00 (타임세일 사용시 필수)
61   | TimeSalePrice              | 타임세일가(쿠폰적용가) | Int(10)             |      | 타임세일가 또는 쿠폰할인액이 적용된 금액<br>(타임세일 기능 사용시 필수)
62   | TimeSaleViewType           | 타이머 노출여부        | enum(0,1)           |      | 0:노출안함, 1:노출
63   | TimeSaleSubjectTag         | 타임세일 말머리        | Text                |      | 상품명 앞에 노출될 말머리
64   | ItemCertification          | KC인증정보 유형        | Varchar(200)        |      | 부록 3. KC인증유형표 참조 (텍스트로 전송)
65   | ItemCertificationInfo      | KC인증 상세(인증번호등)| Varchar(200)        |      | KC인증유형에 따라 입력여부 달라짐
66   | OptIf                      | 옵션API사용유무        | Varchar(1)          |      | 옵션등록 API사용할경우 반드시 "Y"로 설정. UnitInfo 및 기본옵션 삽입안됨.

### Response Data(XML)
순번 | 필드명          | 필드설명            | CDATA | 비고
---- | --------------- | ------------------- | ----- | ----
1    | Result          | 결과                |       | SUCC or FAIL
2    | ItemPartnerCode | 상품품번            |       |
3    | ItemGoodCode    | LATELY 상품고유번호 |       |
4    | ItemNo          | 업체 상품고유번호   |       |
5    | Msg             | 결과메시지          | 사용  |

## 2-6-1. 상품 승인여부 조회
- Interface Name : GetGoodsConfirm
- Description : 특정 상품의 승인 여부를 확인합니다.

### Request Data (POST)
순번 | 필드명       | 필드설명            | 타입        | 필수 | 비고
---- | ------------ | ------------------- | ----------- | ---- | ----
1    | LinkerID     | Link 연동 ID        | Varchar(15) | 필수 |
2    | UserID       | 공급사 아이디       | Varchar(20) | 필수 |
3    | UserPW       | 공급사 비밀번호     | Varchar(20) | 필수 |
4    | ItemGoodCode | LATELY 상품고유번호 | Int(10)     | 필수 |

### Response Data(XML)
순번 | 필드명       | 필드설명            | CDATA | 비고
---- | ------------ | ------------------- | ----- | ----
1    | ItemGoodCode | LATELY 상품고유번호 |       |
2    | ItemConfirm  | 승인여부            | 사용  | 승인완료/승인요청/상품대기

## 2-6-2. 상품 정보 조회
- Interface Name : GetGoodsInfo
- Description : 특정 상품의 정보를 조회합니다.

### Request Data (POST)
순번 | 필드명       | 필드설명            | 타입        | 필수 | 비고
---- | ------------ | ------------------- | ----------- | ---- | ----
1    | LinkerID     | Link 연동 ID        | Varchar(15) | 필수 |
2    | UserID       | 공급사 아이디       | Varchar(20) | 필수 |
3    | UserPW       | 공급사 비밀번호     | Varchar(20) | 필수 |
4    | ItemGoodCode | LATELY 상품고유번호 | Int(10)     |      | ItemGoodCode / ItemNo 둘중 하나 반드시 입력
5    | ItemNo       | 업체 상품고유번호   | Int(10)     |      | 

### Response Data(XML)
순번 | 필드명                 | 필드설명             | CDATA | 비고
---- | ---------------------- | -------------------- | ----- | ----
1    | ItemGoodCode           | LATELY 상품고유번호  |       | 
2    | ItemName               | 상품명               |       | 
3    | ItemNo                 | 업체 상품고유번호    |       | 
4    | RegDate                | 상품등록일           |       | 
5    | ItemPartnerCode        | 상품품번             |       | 
6    | ItemCategory           | 카테고리             |       | 
7    | ItemBrand              | 브랜드               |       | 
8    | Itemkeyword            | 검색어               |       | 
9    | ItemMaker              | 제조사(제조자)       |       | 
10   | ItemMadeIn             | 원산지               |       | 
11   | ItemDesc               | 상품간단설명         |       | 
12   | ItemDescDetail         | 상품상세설명         |       | 
13   | ItemImage              | 상품이미지           |       | 
14   | ItemCount              | 상품수량(재고)       |       | 
15   | TaxYn                  | 과세여부             |       | 
16   | BuyPrice               | 공급가               |       | 
17   | SalePrice              | 판매가               |       | 
18   | ConsumerPrice          | 소비자가             |       | 
19   | DeliveryCharge         | 배송비 구분          |       | 
20   | Delfee                 | 배송비               |       | 
21   | Unittype               | 옵션출력방식         |       | 
22   | UnitInfo               | 옵션정보             |       | 
23   | SaleStatus             | 판매상태             |       | 
24   | StockYn                | 재고 차감 사용여부   |       | 
25   | ItemGoodsRequired      | 필수입력그룹코드     |       | 
26   | ItemMatiere            | 제품소재             |       | 
27   | ItemColors             | 색상                 |       | 
28   | ItemSizes              | 치수 또는 크기       |       | 
29   | ItemKinds              | 종류                 |       | 
30   | ItemVolume             | 용량 또는 중량       |       | 
31   | ItemSpec1              | 제품주요사양         |       | 
32   | ItemSpec2              | 제품세부사양         |       | 
33   | ItemUseAge             | 사용연령             |       | 
34   | ItemEqualModelLaunchdt | 동일모델의 출시 년월 |       | 
35   | ItemServiceLife        | 사용기한             |       | 
36   | Launchdate             | 제조년월             |       | 
37   | ItemUsages             | 사용방법             |       | 
38   | ItemIngredient         | 주요성분             |       | 
39   | ItemWarranty           | 품질인증여부         |       | 
40   | ItemCaution            | 취급 시 주의사항     |       | 
41   | ItemQualityAssurance   | 품질보증기준         |       | 
42   | ItemNoRefund           |                      |       | 
43   | ItemReturnQualityAss   |                      |       | 
44   | ItemCompensation       |                      |       | 
45   | ItemTroubleShooting    |                      |       | 
46   | ItemAsName             | AS 책임자            |       | 
47   | ItemAsTel              | AS 전화번호          |       | 


## 2-7. 상품 등록 고유번호 조회
- Interface Name : GetGoodsCode
- Description : 등록되어 있는 상품의 고유번호를 조회합니다.

### Request Data (POST)
순번 | 필드명       | 필드설명            | 타입        | 필수 | 비고
---- | ------------ | ------------------- | ----------- | ---- | ----
1    | LinkerID     | Link 연동 ID        | Varchar(15) | 필수 |
2    | UserID       | 공급사 아이디       | Varchar(20) | 필수 |
3    | UserPW       | 공급사 비밀번호     | Varchar(20) | 필수 |
4    | ItemGoodCode | LATELY 상품고유번호 | Int(10)     |      | ItemGoodCode, ItemNo 중 한가지 이상 반드시 입력
5    | ItemNo       | 업체 상품고유번호   | Int(10)     |      |

### Response Data(XML)
순번 | 필드명       | 필드설명            | CDATA | 비고
---- | ------------ | ------------------- | ----- | ----
1    | ItemGoodCode | LATELY 상품고유번호 |       |
2    | ItemNo       | 업체 상품고유번호   |       |
3    | ItemConfirm  | 상품 승인여부       | 사용  | 승인완료/승인요청/상품대기

## 2-8. 전상품 고유번호 조회
- Interface Name : GetGoodsList
- Description : 등록되어 있는 모든 상품의 고유번호를 조회합니다.

### Request Data (POST)
순번 | 필드명       | 필드설명            | 타입        | 필수 | 비고
---- | ------------ | ------------------- | ----------- | ---- | ----
1    | LinkerID     | Link 연동 ID        | Varchar(15) | 필수 |
2    | UserID       | 공급사 아이디       | Varchar(20) | 필수 |
3    | UserPW       | 공급사 비밀번호     | Varchar(20) | 필수 |

### Response Data(XML)
순번 | 필드명       | 필드설명            | CDATA | 비고
---- | ------------ | ------------------- | ----- | ----
1    | ItemGoodCode | LATELY 상품고유번호 |       |
1    | ItemName     | 상품명              | 사용  |
2    | ItemNo       | 업체 상품고유번호   |       |
3    | RegDate      | 등록일              |       |

## 2-9. 옵션조회
- Interface Name : GetOption
- Description : 옵션을 조회합니다.

### Request Data (POST)
순번 | 필드명         | 필드설명            | 타입        | 필수 | 비고
---- | -------------- | ------------------- | ----------- | ---- | ----
1    | LinkerID       | Link 연동 ID        | Varchar(15) | 필수 |
2    | UserID         | 공급사 아이디       | Varchar(20) | 필수 |
3    | UserPW         | 공급사 비밀번호     | Varchar(20) | 필수 |
4    | ItemOptionCode | 옵션코드            | Int(10)     | 필수 |

### Response Data(XML)
순번 | 필드명             | 필드설명            | CDATA | 비고
---- | ------------------ | ------------------- | ----- | ----
1    | ItemGoodCode       | LATELY 상품고유번호 |       |
2    | ItemOptionCode     | 옵션고유번호        |       |
3    | OptName1           | 옵션1               | 사용  |
4    | OptName2           | 옵션2               | 사용  |
5    | ItemOptionPrice    | 판매가              |       |
6    | ItemOptionConsumer | 정가                |       |
7    | ItemOptionSupply   | 공급가              |       |
8    | ItemOptionStock    | 재고                |       |

## 2-10. 상품옵션조회
- Interface Name : GetGoodsOption
- Description : 해당상품에 등록되어 있는 전체 옵션을 조회합니다.

### Request Data (POST)
순번 | 필드명         | 필드설명            | 타입        | 필수 | 비고
---- | -------------- | ------------------- | ----------- | ---- | ----
1    | LinkerID       | Link 연동 ID        | Varchar(15) | 필수 |
2    | UserID         | 공급사 아이디       | Varchar(20) | 필수 |
3    | UserPW         | 공급사 비밀번호     | Varchar(20) | 필수 |
4    | ItemGoodsCode  | LATELY 상품고유번호 | Int(10)     | 필수 |

### Response Data(XML)
순번 | 필드명             | 필드설명            | CDATA | 비고
---- | ------------------ | ------------------- | ----- | ----
1    | ItemOptionCode     | 옵션고유번호        |       |
2    | OptName1           | 옵션1               | 사용  |
3    | OptName2           | 옵션2               | 사용  |
4    | ItemOptionPrice    | 판매가              |       |
5    | ItemOptionConsumer | 정가                |       |
6    | ItemOptionSupply   | 공급가              |       |
7    | ItemOptionStock    | 재고                |       |

## 2-11. 옵션등록/수정
- Interface Name : Option
- Description : 옵션을 등록/수정 합니다.
- 옵션별 가격은 추후 구현예정입니다.

### Request Data (POST)
순번 | 필드명         | 필드설명            | 타입        | 필수 | 비고
---- | -------------- | ------------------- | ----------- | ---- | ----
1    | LinkerID       | Link 연동 ID        | Varchar(15) | 필수 |
2    | UserID         | 공급사 아이디       | Varchar(20) | 필수 |
3    | UserPW         | 공급사 비밀번호     | Varchar(20) | 필수 |
4    | ItemGoodsCode  | LATELY 상품고유번호 | Int(10)     | 필수 |
5    | ItemOptionCode | 옵션고유번호        | Int(10)     |      | 수정시에만 입력.
6    | SalePrice      | 판매가              | Int(10)     | 필수 |
7    | ConsumerPrice  | 소비자가            | Int(10)     | 필수 |
8    | BuyPrice       | 공급가              | Int(10)     | 필수 |
9    | OptName1       | 옵션1               | Varchar(20) | 필수 |
10   | OptName2       | 옵션2               | Varchar(20) |      |
11   | Stock          | 수량                | Int(10)     | 필수 |

### Response Data(XML)
순번 | 필드명          | 필드설명        | CDATA | 비고
---- | --------------- | --------------- | ----- | ----
1    | Result          | 결과            |       | SUCC or FAIL
2    | ItemGoodCode    | 상품고유번호    |       |
3    | ItemOptionCode  | 옵션고유번호    |       |
4    | Msg             | 결과메시지      | 사용  |

## 2-12. 옵션삭제
- Interface Name : DelOption
- Description : 해당 옵션을 삭제합니다.

### Request Data (POST)
순번 | 필드명         | 필드설명            | 타입        | 필수 | 비고
---- | -------------- | ------------------- | ----------- | ---- | ----
1    | LinkerID       | Link 연동 ID        | Varchar(15) | 필수 |
2    | UserID         | 공급사 아이디       | Varchar(20) | 필수 |
3    | UserPW         | 공급사 비밀번호     | Varchar(20) | 필수 |
4    | ItemOptionCode | 옵션고유번호        | Int(10)     | 필수 |

### Response Data(XML)
순번 | 필드명         | 필드설명     | CDATA | 비고
---- | -------------- | ------------ | ----- | ----
1    | Result         | 옵션고유번호 |       | SUCC or FAIL
2    | ItemOptionCode | 옵션고유번호 |       |
3    | Msg            | 결과메세지   | 사용  |

# 3. 주문관련 API

## 3-1. 주문리스트
- Interface Name : OrderInfo
- Description : 결제완료(입금확인)된 주문리스트 조회 합니다.

### Request Data (POST)
순번 | 필드명      | 필드설명        | 타입        | 필수 | 비고
---- | ----------- | --------------- | ----------- | ---- | ----
1    | LinkerID    | Link 연동 ID    | Varchar(15) | 필수 |
2    | UserID      | 공급사 아이디   | Varchar(20) | 필수 |
3    | UserPW      | 공급사 비밀번호 | Varchar(20) | 필수 |
4    | StartDt     | 검색 시작일자   | Date(+HH)   | 필수 | 구매확정일 기준. YYYY-MM-DD (시간추가가능 YYYY-MM-DD-HH)
5    | EndDt       | 검색 종료일자   | Date(+HH)   | 필수 | 구매확정일 기준. YYYY-MM-DD (시간추가가능 YYYY-MM-DD-HH)
6    | OrderId     | 주문번호        | bigint(20)  |      | 주문번호
7    | OrderItemID | 주문상세번호    | int(10)     |      | 주문상세번호
8    | vmode       | 주문상태구분    | Varchar(10) |      | all:입금대기,입금확인,배송준비중 / pre:배송준비중 / null:입금확인

### Response Data(XML)
순번 | 필드명            | 필드설명              | CDATA | 비고
---- | ----------------- | --------------------- | ----- | ----
1    | OrderID           | 주문번호              |       |
2    | OrderItemID       | 주문상세번호          |       | (고유번호)
3    | OrderDat          | 주문일자              | 사용  | 구버전 API용
4    | OrderDate         | 주문일자              | 사용  |
5    | PayDate           | 결제일                | 사용  |
6    | OrderStep1        | 주문 상태             |       | 코드 3. 주문 상태 코드
7    | OrderStep2        | 주문 취소 상태        |       | 코드 4. 취소 상태 코드
8    | OrderExchange     | 교환상태              |       | 코드 5. 교환 상태 코드
9    | OrderStatus       | 주문 상태 명          | 사용  |
10   | MallProductID     | LATELY 상품고유번호   |       |
11   | PtnProductID      | 연동업체 상품고유번호 |       |
12   | PrdNM             | 상품명                | 사용  |
13   | OptNo             | 옵션번호              |       |
14   | OptNM             | 옵션정보              | 사용  | OptNm1 + OptNm2 + AddOpt(옵션없는 상품인 경우 빈값)
15   | OptNm1            | 옵션명1               | 사용  | 옵션명 분리 가능한경우 제공
16   | OptNm2            | 옵션명2               | 사용  | 옵션명 분리 가능한경우 제공
17   | AddOpt            | 추가옵션정보          | 사용  | 추가옵션이 있는경우 제공
18   | Qty               | 주문수량              |       |
19   | CancelQty         | 취소된수량            |       | 부분 수량취소된 주문은 OrderClaim에서 별도 수집가능
20   | SalePrice         | 판매가                |       | 공급사에서 제공한 판매가
21   | BuyPirce          | 공급가                |       |
22   | PayPrice          | 결재가                |       | 실제결재금액<br>판매단가 * 수량 – 할인<br>(쿠폰할인+타임세일할인액+멤버할인)
23   | DcPrice           | 할인가                |       | 쿠폰+멤버할인
24   | TimeSaleDc        | 타임세일할인액        |       | 타임세일할인액이 있는경우 제공
25   | DeliveryPackgeNum | 묶음배송코드          |       |
26   | DeliveryType      | 배송정보              | 사용  |
27   | DeliveryPrice     | 배송비                |       |
28   | DeliveryNum       | 택배사[송장번호]      |       |
29   | BuyerName         | 주문자                | 사용  |
30   | BuyerTel          | 주문자 전화번호       | 사용  |
31   | BuyerHp           | 주문자 휴대전화       | 사용  |
32   | BuyerMail         | 주문자 이메일         |       |
33   | RcvName           | 수취인                | 사용  |
34   | RcvTel            | 수취인 전화번호       |       |
35   | RcvHp             | 수취인 휴대전화       |       |
36   | RcvZip            | 수취인 우편번호       |       |
37   | RcvAddr           | 배송지 주소           | 사용  |
38   | Memo              | 배송 메세지           | 사용  |

## 3-2. 구매확정 주문리스트
- Interface Name : OrderBuyConfirm
- Description : 구매확정된 주문리스트 조회 합니다.<br>취소/교환건 제외 (업체정산기준:구매확정)

### Request Data (POST)
순번 | 필드명   | 필드설명        | 타입        | 필수 | 비고
---- | -------- | --------------- | ----------- | ---- | ----
1    | LinkerID | Link 연동 ID    | Varchar(15) | 필수 |
2    | UserID   | 공급사 아이디   | Varchar(20) | 필수 |
3    | UserPW   | 공급사 비밀번호 | Varchar(20) | 필수 |
4    | StartDt  | 검색 시작일자   | Date(+HH)   | 필수 | 구매확정일 기준. YYYY-MM-DD (시간추가가능 YYYY-MM-DD-HH)
5    | EndDt    | 검색 종료일자   | Date(+HH)   | 필수 | 구매확정일 기준. YYYY-MM-DD (시간추가가능 YYYY-MM-DD-HH)

### Response Data(XML)
순번 | 필드명            | 필드설명            | CDATA | 비고
---- | ----------------- | ------------------- | ----- | ----
1    | OrderID           | 주문번호            |       |
2    | OrderItemID       | 주문상세번호        |       | (고유번호)
3    | OrderDate         | 주문일자            | 사용  |
4    | PayDate           | 결제일              | 사용  |
5    | BuyConfirmDate    | 구매확정일          | 사용  |
6    | OrderStatus       | 주문 상태           | 사용  |
7    | MallProductID     | LATELY 상품고유번호 |       |
8    | PrdNM             | 상품명              | 사용  |
9    | OptNM             | 주문옵션정보        | 사용  |
10   | Qty               | 주문수량            |       |
11   | SalePrice         | 판매가              |       | 공급사에서 제공한 판매가
12   | BuyPirce          | 공급가              |       |
13   | PayPrice          | 결재가              |       | 실제결재금액<br>판매단가 * 수량 – 할인<br>(쿠폰할인+타임세일할인액+멤버할인)
14   | DeliveryPackgeNum | 묶음배송코드        |       |
15   | DeliveryType      | 배송정보            | 사용  |
16   | DeliveryPrice     | 배송비              |       |
17   | DeliveryNum       | 택배사[송장번호]    |       |
18   | BuyerName         | 주문자              | 사용  |
19   | BuyerTel          | 주문자 전화번호     | 사용  |
20   | BuyerHp           | 주문자 휴대전화     | 사용  |
21   | BuyerMail         | 주문자 이메일       |       |
22   | RcvName           | 수취인              | 사용  |
23   | RcvTel            | 수취인 전화번호     |       |
24   | RcvHp             | 수취인 휴대전화     |       |
25   | RcvZip            | 수취인 우편번호     |       |
26   | RcvAddr           | 배송지 주소         | 사용  |
27   | Memo              | 배송 메세지         | 사용  |

## 3-3. 발주처리
- Interface Name : OrderConfirm
- Description : 입금 확인된 주문 건을 발주처리(배송준비중) 합니다.

### Request Data (POST)
순번 | 필드명      | 필드설명        | 타입        | 필수 | 비고
---- | ----------- | --------------- | ----------- | ---- | ----
1    | LinkerID    | Link 연동 ID    | Varchar(15) | 필수 |
2    | UserID      | 공급사 아이디   | Varchar(20) | 필수 |
3    | UserPW      | 공급사 비밀번호 | Varchar(20) | 필수 |
4    | OrderID     | 주문번호        | BigInt(20)  | 필수 |
5    | OrderItemID | 주문상세번호    | Int(10)     | 필수 |

### Response Data(XML)
순번 | 필드명      | 필드설명     | CDATA | 비고
---- | ----------- | ------------ | ----- | ----
1    | Result      | 결과         |       | SUCC or FAIL
2    | OrderID     | 주문번호     |       |
3    | OrderItemID | 주문상세번호 |       |
4    | ReturnCD    | 결과값       |       |
5    | Msg         | 결과메시지   | 사용  |

## 3-4. 배송지연처리
- Interface Name : DeliveryDelay
- Description : 입금확인 후 3일이내 상품발송(배송)을 하지 못할 경우 발송지연 안내를 처리합니다.

### Request Data (POST)
순번 | 필드명      | 필드설명         | 타입         | 필수 | 비고
---- | ----------- | ---------------- | ------------ | ---- | ----
1    | LinkerID    | Link 연동 ID     | Varchar(15)  | 필수 |
2    | UserID      | 공급사 아이디    | Varchar(20)  | 필수 |
3    | UserPW      | 공급사 비밀번호  | Varchar(20)  | 필수 |
4    | OrderID     | 주문번호         | BigInt(20)   | 필수 |
5    | OrderItemID | 주문상세번호     | Int(10)      | 필수 |
6    | DelayCd     | 발송지연사유     | Char(2)      | 필수 | 코드 6. 발송지연사유 코드
7    | DelayDt     | 발송기한         | Date         | 필수 |
8    | DelayDetail | 발송지연상세사유 | Varchar(200) |      |

### Response Data(XML)
순번 | 필드명      | 필드설명     | CDATA | 비고
---- | ----------- | ------------ | ----- | ----
1    | Result      | 결과         |       | SUCC or FAIL
2    | OrderID     | 주문번호     |       |
3    | OrderItemID | 주문상세번호 |       |
4    | ReturnCD    | 결과값       |       |
5    | Msg         | 결과메시지   | 사용  |

## 3-5. 발송처리
- Interface Name : OrderInvoice (+OrderInvoce 동일)
- Description : 택배사 및 송장번호를 등록하여 발송(배송) 처리합니다. 발송처리는 입금확인/발주확인 상태에서만 가능합니다.

### Request Data (POST)
순번 | 필드명      | 필드설명        | 타입         | 필수 | 비고
---- | ----------- | --------------- | ------------ | ---- | ----
1    | LinkerID    | Link 연동 ID    | Varchar(15)  | 필수 |
2    | UserID      | 공급사 아이디   | Varchar(20)  | 필수 |
3    | UserPW      | 공급사 비밀번호 | Varchar(20)  | 필수 |
4    | OrderID     | 주문번호        | BigInt(20)   | 필수 |
5    | OrderItemID | 주문상세번호    | Int(10)      | 필수 |
6    | Delv_Cd     | 택배사 코드     | Char(2)      | 필수 | 2-3. 택배사 리스트 참고
7    | Invoice     | 송장번호        | Int(10)      | 필수 | "-"제외, 숫자만 입력
8    | Delv_date   | 발송일          | Date         |      |

### Response Data(XML)
순번 | 필드명      | 필드설명     | CDATA | 비고
---- | ----------- | ------------ | ----- | ----
1    | Result      | 결과         |       | SUCC or FAIL
2    | OrderID     | 주문번호     |       |
3    | OrderItemID | 주문상세번호 |       |
4    | Msg         | 결과메시지   | 사용  |

## 3-6. 주문취소/반품/교환리스트
- Interface Name : OrderClaim (+OrderClame 동일)
- Description : 입금 완료된 주문건에 대한 주문 취소 리스트입니다.

### Request Data (POST)
순번 | 필드명   | 필드설명        | 타입        | 필수 | 비고
---- | -------- | --------------- | ----------- | ---- | ----
1    | LinkerID | Link 연동 ID    | Varchar(15) | 필수 |
2    | UserID   | 공급사 아이디   | Varchar(20) | 필수 |
3    | UserPW   | 공급사 비밀번호 | Varchar(20) | 필수 |
4    | StartDt  | 검색 시작일자   | Date(+HH)   | 필수 | 구매확정일 기준. YYYY-MM-DD (시간추가가능 YYYY-MM-DD-HH)
5    | EndDt    | 검색 종료일자   | Date(+HH)   | 필수 | 구매확정일 기준. YYYY-MM-DD (시간추가가능 YYYY-MM-DD-HH)

### Response Data(XML)
순번 | 필드명          | 필드설명               | CDATA | 비고
---- | --------------- | ---------------------- | ----- | ----
1    | OrderID         | 주문번호               |       |
2    | OrderItemID     | 주문상세번호           |       | (고유번호)
3    | CancelNo        | 취소번호               |       |
4    | OrderStep1      | 주문 상태              |       | 코드 3. 주문 상태 코드
5    | OrderStep2      | 주문 취소 상태         |       | 코드 4. 취소 상태 코드
6    | OrderExchange   | 교환상태               |       | 코드 5. 교환 상태 코드
7    | OrderStatus     | 주문 상태 명           | 사용  |
8    | OrderDate       | 주문일자               | 사용  |
9    | OrderCancelDate | 취소/반품/교환신청일자 | 사용  |
10   | OrderRefundDate | 취소/반품/교환완료일자 | 사용  |
11   | MallProductID   | LATELY 상품고유번호    |       |
12   | PtnProductID    | 연동업체 상품고유번호  |       |
13   | PrdNM           | 상품명                 | 사용  |
14   | OptNo           | 옵션번호               | 사용  |
15   | OptNM           | 옵션정보               | 사용  |
16   | Qty             | 주문수량               |       |
17   | SalePrice       | 판매가                 |       | 공급사에서 제공한 판매가
18   | BuyerName       | 주문자                 | 사용  |
19   | Memo            | 취소/반품/교환사유     | 사용  |
20   | ClaimCode       | 클레임코드             | 사용  | 코드 7. 클레임 코드 참조
21   | OrderOldID      | 원주문상세번호         | 사용  | 부분취소시 원주문상세번호(OrderItemID)
22   | OriOpt          | 원주문옵션             | 사용  | 교환건일경우 사용


## 3-7. 구매확정 취소(반품)리스트
- Interface Name : OrderConfirmClaim
- Description : 구매확정건에 대한 주문 취소(반품) 리스트입니다.

### Request Data (POST)
순번 | 필드명   | 필드설명        | 타입        | 필수 | 비고
---- | -------- | --------------- | ----------- | ---- | ----
1    | LinkerID | Link 연동 ID    | Varchar(15) | 필수 |
2    | UserID   | 공급사 아이디   | Varchar(20) | 필수 |
3    | UserPW   | 공급사 비밀번호 | Varchar(20) | 필수 |
4    | StartDt  | 검색 시작일자   | Date(+HH)   | 필수 | 주문접수일 기준. YYYY-MM-DD (시간추가가능 YYYY-MM-DD-HH)
5    | EndDt    | 검색 종료일자   | Date(+HH)   | 필수 | 주문접수일 기준. YYYY-MM-DD (시간추가가능 YYYY-MM-DD-HH)

### Response Data(XML)
순번 | 필드명          | 필드설명               | CDATA | 비고
---- | --------------- | ---------------------- | ----- | ----
1    | OrderID         | 주문번호               |       |
2    | OrderItemID     | 주문상세번호           |       | (고유번호)
3    | OrderStatus     | 주문 상태 명           | 사용  |
4    | OrderDate       | 주문일자               | 사용  |
5    | OrderCancelDate | 취소/반품/교환신청일자 | 사용  |
6    | OrderRefundDate | 취소/반품/교환완료일자 | 사용  |
7    | MallProductID   | LATELY 상품고유번호    |       |
8    | PrdNM           | 상품명                 | 사용  |
9    | OptNM           | 주문옵션정보           | 사용  |
10   | BuyerName       | 주문자                 | 사용  |
11   | Qty             | 주문수량               |       |
12   | SalePrice       | 판매가                 |       | 공급사에서 제공한 판매가
13   | BuyPirce        | 공급사                 |       |
14   | PayPrice        | 결재가                 |       | 실제결재금액<br>판매단가 * 수량 – 할인<br>(쿠폰할인+타임세일할인액+멤버할인)
15   | Memo            | 취소/반품/교환사유     | 사용  |

## 3-8. 판매거부(배송전 주문취소 요청)
- Interface Name : OrderReject
- Description : 입금대기/입금확인 상태의 주문건이 가격오류 또는 품절 시 해당 상세사유를 작성해 판매거부 합니다.

### Request Data (POST)
순번 | 필드명      | 필드설명        | 타입         | 필수 | 비고
---- | ----------- | --------------- | ------------ | ---- | ----
1    | LinkerID    | Link 연동 ID    | Varchar(15)  | 필수 |
2    | UserID      | 공급사 아이디   | Varchar(20)  | 필수 |
3    | UserPW      | 공급사 비밀번호 | Varchar(20)  | 필수 |
4    | OrderID     | 주문번호        | BigInt(20)   | 필수 |
5    | OrderItemID | 주문상세번호    | Int(10)      | 필수 | (고유번호)
6    | RejectCd    | 판매거부코드    | Char(3)      | 필수 | 코드 7. 판매거부사유 코드
7    | RejectMsg   | 상세사유        | Varchar(200) |      |

### Response Data(XML)
순번 | 필드명      | 필드설명     | CDATA | 비고
---- | ----------- | ------------ | ----- | ----
1    | Return      | 결과         |       | SUCC or FAIL
2    | OrderID     | 주문번호     |       |
3    | OrderItemID | 주문상세번호 |       |
4    | ReturnCD    | 결과값       |       |
5    | Msg         | 결과메시지   | 사용  |

# 4. 문의관련 API

## 4-1. 상품문의
- Interface Name : GetGoodsQna
- Description : 상품관련 문의글을 조회합니다.

### Request Data (POST)
순번 | 필드명   | 필드설명        | 타입        | 필수 | 비고
---- | -------- | --------------- | ----------- | ---- | ----
1    | LinkerID | Link 연동 ID    | Varchar(15) | 필수 |
2    | UserID   | 공급사 아이디   | Varchar(20) | 필수 |
3    | UserPW   | 공급사 비밀번호 | Varchar(20) | 필수 |
4    | StartDt  | 검색 시작일자   | Date        | 필수 | 주문접수일 기준. YYYY-MM-DD
5    | EndDt    | 검색 종료일자   | Date        | 필수 | 주문접수일 기준. YYYY-MM-DD

### Response Data(XML)
순번 | 필드명       | 필드설명        | CDATA | 비고
---- | ------------ | --------------- | ----- | ----
1    | QnaID        | 상품문의 번호   |       | SUCC or FAIL
2    | ItemGoodCode | LATELY 상품번호 |       |
3    | QnaParent    | 부모글 번호     |       |
4    | QnaSubject   | 제목            | 사용  |
5    | QnaContents  | 내용            | 사용  |
6    | QnaDate      | 작성일자        |       |
7    | QnaIP        | 작성IP          | 사용  |
8    | QnaName      | 작성자          | 사용  |
9    | QnaSecretYn  | 비밀글여부      |       | 001:모두공개, 002:비밀글
10   | QnaEmail     | 이메일          | 사용  |
11   | QnaPhone     | 연락처          | 사용  |

## 4-2. 상품문의 답변
- Interface Name : GoodsQna
- Description : 상품관련 문의 글에 대한 답변을 전송합니다. (답변만 등록가능)

### Request Data (POST)
순번 | 필드명       | 필드설명        | 타입          | 필수 | 비고
---- | ------------ | --------------- | ------------- | ---- | ----
1    | LinkerID     | Link 연동 ID    | Varchar(15)   | 필수 |
2    | UserID       | 공급사 아이디   | Varchar(20)   | 필수 |
3    | UserPW       | 공급사 비밀번호 | Varchar(20)   | 필수 |
4    | QnaParent    | 부모글 일련번호 | Int(10)       | 필수 | 답변 시 사용
5    | QnaID        | 답변글 일련번호 | Int(10)       | 필수 | 수정 시 사용
6    | ItemGoodCode | LATELY 상품번호 | Int(10)       |      |
7    | QnaSubject   | 제목            | Varchar(200)  | 필수 |
8    | QnaContents  | 내용            | Text          | 필수 |
9    | QnaIP        | 작성IP          | Varchar(15)   | 필수 |
10   | QnaName      | 작성자          | Varchar(20)   | 필수 |
11   | QnaSecretYn  | 비밀글여부      | Enum(001,002) |      | 001:모두공개, 002:비밀글

### Response Data(XML)
순번 | 필드명     | 필드설명        | CDATA | 비고
---- | ---------- | --------------- | ----- | ----
1    | Result     | 결과            |       | SUCC or FAIL
2    | QnaID      | 답변글 일련번호 |       |
3    | QnaSubject | 답글제목        | 사용  |
4    | Msg        | 결과메시지      | 사용  |

# 5. Code

## 5-1. 배송비 유형 코드
코드 | 설명         | 비고
---- | ------------ | ----
001  | 무료         |
002  | 착불         | 상품필드 Delfee 필수입력
003  | 기본배송정책 |
004  | 고정배송비   | 상품필드 Delfee 필수입력
005  | 수량별배송비 | 상품필드 Delfee 필수입력

## 5-2. 상품정보 필수입력 그룹
- 상품정보고시에 따른 상품정보 필수입력 코드입니다.

코드 | 설명               | 비고
---- | ------------------ | ----
g0   | 의류               | 부록 6-2. 의류 필수항목 참고
g1   | 구두,신발          | 부록 6-2. 구두,신발 필수항목 참고
g2   | 가방               | 부록 6-2. 가방 필수항목 참고
g3   | 패션잡화           | 부록 6-2. 패션잡화 필수항목 참고
g4   | 화장품             | 부록 6-2. 화장품 필수항목 참고
g5   | 귀금속/보석/시계류 | 부록 6-2. 귀금속/보석/시계류 필수항목 참고
g6   | 영유아용품         | 부록 6-2. 영유아용품 필수항목 참고
g7   | 스포츠용품         | 부록 6-2. 스포츠용품 필수항목 참고
g8   | 가공식품           | 부록 6-2. 가공식품 필수항목 참고
g9   | 침구류             | 부록 6-2. 침구류 필수항목 참고
g10  | 가전               | 부록 6-2. 가전 필수항목 참고
g11  | 주방용품           | 부록 6-2. 주방용품 필수항목 참고
g12  | 수납/청소/생활잡화 | 부록 6-2. 수납/청소/생활잡화 필수항목 참고
g13  | 가구               | 부록 6-2. 가구 필수항목 참고
g14  | 식품(농수산물)     | 부록 6-2. 식품(농수산물) 필수항목 참고
g15  | 건강기능식품       | 부록 6-2. 건강기능식품 필수항목 참고

## 5-3. 상품 주문 상태 코드
코드 | 설명               | 비고
---- | ------------------ | ----
0    | 주문접수(입금대기) |
1    | 입금확인(결재완료) |
2    | 배송준비 중        |
3    | 배송중             |
4    | 배송완료           |
5    | 구매확정           |

## 5-4. 상품 주문 취소 상태 코드
코드 | 설명                  | 비고
---- | --------------------- | ----
0    | 정상주문              |
40   | [취소,반품,환불] 요청 |
41   | [취소,반품,환불] 접수 |
42   | 환불 접수             | 반품일때만
44   | [취소,반품,환불] 완료 |

## 5-5. 교환 상태 코드
-교환은 상품 주문 상태가 "배송중" 이상일때만 사용하며 상품 주문 취소상태랑은 무관하게 진행됩니다.

코드 | 설명       | 비고
---- | ---------- | ----
0    | 정상주문   |
1    | 교환요청   |
2    | 수거완료   |
3    | 재배송준비 |
4    | 재배송중   |
5    | 교환완료   |

## 5-6. 발송지연사유 코드
코드 | 설명       | 비고
---- | ---------- | ----
01   | 상품준비중 |
02   | 주문제작   |
03   | 고객요청   |
04   | 예약발송   |
05   | 기타       |

## 5-7. 판매거부사유 코드
코드 | 설명                  | 비고
---- | --------------------- | ----
001  | 수량부족(품절)        |
002  | 가격 변동             |
003  | 브랜드 자체 판매 거부 |
004  | 기타                  |

## 5-8. 클레임 코드
코드 | 설명                  | 비고
---- | --------------------- | ----
2    | 품절취소              |
3    | 배송지연취소          |
4    | 이중주문취소          |
5    | 시스템오류취소        |
6    | 누락배송              |
7    | 택배분실              |
9    | 기타                  |
10   | 거래미성사            |
11   | 오배송                |
12   | 고객변심(사이즈)      |
13   | 고객변심(컬러)        |
14   | 고객변심(디자인)      |
15   | 고객변심(화면과다름)  |
16   | 고객변심(저품질)      |
17   | 상품불량(변경)        |
18   | 상품불량(파손)        |
19   | 상품불량(봉제불량)    |
20   | 상품불량(오염)        |
21   | 상품불량(포장)        |

# 6. 부록

## 6-1. 상품옵션 전송 방법
- 상품 전송시 옵션 작성 방법 입니다. (주의 : 옵션은 2차옵션 까지만 사용 가능합니다.)

### [ 1차 옵션 등록 ]
- 예) 사이즈가 여러 개인 팬츠

옵션값 | 재고 | 판매가 | 정가   | 공급가 | 적립금
------ | ---- | ------ | ------ | ------ | ------
44     | 50   | 10,000 | 12,000 | 6,000  | 0
55     | 45   | 10,000 | 12,000 | 6,000  | 0
66     | 50   | 10,000 | 12,000 | 6,000  | 0

- 옵션구분명|옵션1^^재고^^판매가^^정가^^공급가^^적립금 (콤마로 구분)<br>▷ 사이즈|44^^50^^10000^^12000^^6000^^0,55^^45^^10000^^12000^^6000^^0,66^^50^^10000^^12000^^6000^^0

### [ 2차 옵션 등록 ]
- 예) 사이즈 및 색상이 여러 가지인 팬츠

44     | 55     | 66     | 재고 | 판매가 | 정가   | 공급가 | 적립금
------ | ------ | ------ | ---- | ------ | ------ | ------ | ------
네이비 | 네이비 | 네이비 | 50   | 10,000 | 12,000 | 6,000  | 0
그레이 | 그레이 | 그레이 | 45   | 10,000 | 12,000 | 6,000  | 0
블랙   | 블랙   | 블랙   | 50   | 10,000 | 12,000 | 6,000  | 0

- 옵션명1/옵션명2|옵션1/옵션2^^재고^^판매가^^정가^^공급가^^적립금 (콤마로 구분)<br>▷ 색상/사이즈|네이비/44^^50^^10000^^12000^^6000^^0,네이비/55^^45^^10000^^12000^^6000^^0,네이비<br>/66^^50^^10000^^12000^^6000^^0,그레이/44^^50^^10000^^12000^^6000^^0,그레이<br>/55^^45^^10000^^12000^^6000^^0,그레이/66^^50^^10000^^12000^^6000^^0,블랙

## 6-2. 상품정보고시 관련 필수 입력 항목

### [g0] 의류 필수 항목
순번 | 항목명                      | 필드명
---- | --------------------------- | ----
1    | 소재                        | ItemMatiere
2    | 색상                        | ItemColors
3    | 치수                        | ItemSizes
4    | 제조사                      | ItemMaker
5    | 제조국                      | ItemMadeIn
6    | 제조년월                    | Launchdate
7    | 세탁방법 및 취급시 주의사항 | ItemCaution
8    | 품질보증기준                | ItemQualityAssurance
9    | AS 책임자                   | ItemAsName
10   | AS 전화번호                 | ItemAsTel

### [g1] 구두/신발 필수 항목
순번 | 항목명                      | 필드명
---- | --------------------------- | ----
1    | 소재                        | ItemMatiere
2    | 색상                        | ItemColors
3    | 치수                        | ItemSizes
4    | 제조사                      | ItemMaker
5    | 제조국                      | ItemMadeIn
6    | 취급시 주의사항             | ItemCaution
7    | 품질보증기준                | ItemQualityAssurance
8    | AS 책임자                   | ItemAsName
9    | AS 전화번호                 | ItemAsTel

### [g2] 가방 필수 항목
순번 | 항목명                      | 필드명
---- | --------------------------- | ----
1    | 소재                        | ItemMatiere
2    | 색상                        | ItemColors
3    | 크기                        | ItemSizes
4    | 제조사                      | ItemMaker
5    | 제조국                      | ItemMadeIn
6    | 취급시 주의사항             | ItemCaution
7    | 종류                        | ItemKinds
8    | 품질보증기준                | ItemQualityAssurance
9    | AS 책임자                   | ItemAsName
10   | AS 전화번호                 | ItemAsTel

### [g3] 패션잡화 필수 항목
순번 | 항목명                      | 필드명
---- | --------------------------- | ----
1    | 소재                        | ItemMatiere
2    | 치수                        | ItemSizes
3    | 제조사                      | ItemMaker
4    | 제조국                      | ItemMadeIn
5    | 취급시 주의사항             | ItemCaution
6    | 종류                        | ItemKinds
7    | 품질보증기준                | ItemQualityAssurance
8    | AS 책임자                   | ItemAsName
9    | AS 전화번호                 | ItemAsTel

### [g4] 화장품 필수 항목
순번 | 항목명                      | 필드명
---- | --------------------------- | ----
1    | 제조자 및 제조판매업자      | ItemMaker
2    | 제조국                      | ItemMadeIn
3    | 취급시 주의사항             | ItemCaution
4    | 용량 또는 중량              | ItemVolume
5    | 제품주요사양                | ItemSpec1
6    | 사용기한                    | ItemServiceLife
7    | 사용방법                    | ItemUsages
8    | 주요성분                    | ItemIngredient
9    | 기능성화장품 심사필유무     | ItemWarranty
9    | 보증서 인증번호             | ItemWarranty_number
11   | 품질보증기준                | ItemQualityAssurance
12   | AS 책임자                   | ItemAsName
13   | AS 전화번호                 | ItemAsTel

### [g5] 귀금속/보석/시계 필수 항목
순번 | 항목명                      | 필드명
---- | --------------------------- | ----
1    | 소재/순도/재질              | ItemMatiere
2    | 치수                        | ItemSizes
3    | 제조사                      | ItemMaker
4    | 제조국                      | ItemMadeIn
5    | 취급시 주의사항             | ItemCaution
6    | 중량                        | ItemVolume
7    | 주요사양                    | ItemSpec1
8    | 보증서 제공여부             | ItemWarranty
9    | 보증서 인증번호             | ItemWarranty_number
10    | 품질보증기준                | ItemQualityAssurance
11   | AS 책임자                   | ItemAsName
12   | AS 전화번호                 | ItemAsTel

### [g6] 영유아용품 필수 항목
순번 | 항목명                      | 필드명
---- | --------------------------- | ----
1    | 소재/순도/재질              | ItemMatiere
2    | 색상                        | ItemColors
3    | 제조사                      | ItemMaker
4    | 제조국                      | ItemMadeIn
5    | 취급방법 및 취급시 주의사항 | ItemCaution
6    | 크기 및 중량                | ItemVolume
7    | KC인증필                    | ItemWarranty
8    | 보증서 인증번호             | ItemWarranty_number
9    | 인증기관                    | ItemWarrantyGov
10    | 사용연령                    | ItemUseAge
11   | 동일모델의 출시년월         | ItemEqualModelLaunchdt
12   | 품명 및 모델명              | ItemPartnerCode
13   | 품질보증기준                | ItemQualityAssurance
14   | AS 책임자                   | ItemAsName
15   | AS 전화번호                 | ItemAsTel

### [g7] 스포츠용품 필수 항목
순번 | 항목명                      | 필드명
---- | --------------------------- | ----
1    | 재질                        | ItemMatiere
2    | 색상                        | ItemColors
3    | 제조사                      | ItemMaker
4    | 제조국                      | ItemMadeIn
5    | 크기 및 중량                | ItemVolume
6    | 제품구성                    | ItemSpec1
7    | 동일모델의 출시년월         | ItemEqualModelLaunchdt
8    | 상품별 세부사양             | ItemSpec2
9    | 품명 및 모델명              | ItemPartnerCode
10   | 품질보증기준                | ItemQualityAssurance
11   | AS 책임자                   | ItemAsName
12   | AS 전화번호                 | ItemAsTel

### [g8] 가공식품 필수 항목
순번 | 항목명                      | 필드명
---- | --------------------------- | ----
1    | 식품의유형                  | ItemKinds
2    | 생산자 및 소재지            | ItemMaker
3    | 제조국                      | ItemMadeIn
4    | 제조년월일,유통기한         | Launchdate
5    | 용량,수량                   | ItemVolume
6    | 원재료 및 함량              | ItemMatiere
7    | 영양성분                    | ItemIngredient
8    | 유전자재조합식품 여부       | ItemGeneticallyMod
9    | 특수용도식품 사전심의필     | ItemSpecialFood
10   | 수입식품여부                | ItemImport
11   | AS 전화번호                 | ItemAsTel

### [g9] 침구류 필수 항목
순번 | 항목명                      | 필드명
---- | --------------------------- | ----
1    | 소재                        | ItemMatiere
2    | 치수                        | ItemSizes
3    | 제조사                      | ItemMaker
4    | 제조국                      | ItemMadeIn
5    | 취급시 주의사항             | ItemCaution
6    | 품질보증기준                | ItemQualityAssurance
7    | 제품구성                    | ItemKinds
8    | AS 책임자                   | ItemAsName
9    | AS 전화번호                 | ItemAsTel

### [g10] 가전 필수 항목
순번 | 항목명                      | 필드명
---- | --------------------------- | ----
1    | 품명 및 모델명              | ItemPartnerCode
2    | 정격전압/소비전력/에너지소비| ItemSpec1
3    | KC인증필                    | ItemWarranty
4    | 보증서 인증번호             | ItemWarranty_number
5    | 동일모델의 출시년월         | ItemEqualModelLaunchdt
6    | 크기                        | ItemSizes
7    | 품질보증기준                | ItemQualityAssurance
8    | 제조사                      | ItemMaker
9    | 제조국                      | ItemMadeIn
10   | 취급시 주의사항             | ItemCaution
11   | AS 책임자                   | ItemAsName
12   | AS 전화번호                 | ItemAsTel

### [g11] 주방용품 필수 항목
순번 | 항목명                      | 필드명
---- | --------------------------- | ----
1    | 품명 및 모델명              | ItemPartnerCode
2    | 재질                        | ItemMatiere
3    | 구성품                      | ItemKinds
4    | 동일모델의 출시년월         | ItemEqualModelLaunchdt
5    | 크기                        | ItemSizes
6    | 품질보증기준                | ItemQualityAssurance
7    | 제조사                      | ItemMaker
8    | 식품위생법에 따른 수입신고  | ItemImport
9    | 제조국                      | ItemMadeIn
10   | AS 책임자                   | ItemAsName
11   | AS 전화번호                 | ItemAsTel

### [g12] 수납/청소/생활잡화 필수 항목
순번 | 항목명                      | 필드명
---- | --------------------------- | ----
1    | 품명 및 모델명              | ItemPartnerCode
2    | 인증,허가 사항              | ItemQualityAssurance
3    | 제조사                      | ItemMaker
4    | 제조국                      | ItemMadeIn
5    | 제품안전인증번호            | ItemWarranty
6    | 보증서 인증번호             | ItemWarranty_number
7    | AS 책임자                   | ItemAsName
8    | AS 전화번호                 | ItemAsTel

### [g13] 가구 필수 항목
순번 | 항목명                      | 필드명
---- | --------------------------- | ----
1    | 품명 및 모델명              | ItemPartnerCode
2    | 색상                        | ItemColors
3    | KC인증필                    | ItemWarranty
4    | 보증서 인증번호             | ItemWarranty_number
5    | 구성품                      | ItemKinds
6    | 재질                        | ItemMatiere
7    | 제조사                      | ItemMaker
8    | 제조국                      | ItemMadeIn
9    | 크기                        | ItemSizes
10   | 배송 설치비용               | ItemServiceLife
11   | 인증,허가 사항              | ItemQualityAssurance
12   | AS 책임자                   | ItemAsName
13   | AS 전화번호                 | ItemAsTel

### [g14] 식품(농수산물) 필수 항목
순번 | 항목명                                                       | 필드명
---- | ------------------------------------------------------------ | ----
1    | 포장단위별 용량(중량), 수량, 크기                            | ItemVolume
2    | 생산자, 수입품의 경우 수입자를 함께 표기                     | ItemMaker
3    | 농수산물의 원산지 표시에 관한 법률에 따른 원산지             | ItemMadeIn
4    | 제조연월일(포장일 또는 생산연도), 유통기한 또는 품질유지기한 | Launchdate
5    | 상품구성                                                     | ItemSpec1
6    | 관련법상 표시사항                                            | ItemSpec2
7    | 소비자상담 관련 전화번호                                     | ItemAsTel

### [g15] 건강기능식품 필수 항목
순번 | 항목명                                                                            | 필드명
---- | --------------------------------------------------------------------------------- | ----
1    | 식품의 유형                                                                       | ItemKinds
2    | 생산자 및 소재지(수입품의 경우 생산자, 수입자 및 제조국)                          | ItemMaker
3    | 제조연월일, 유통기한 또는 품질유지기한                                            | Launchdate
4    | 포장단위별 용량(중량), 수량                                                       | ItemVolume
5    | 원재료명 및 함량(농수산물의 원산지 표시에 관한 법률에 따른 원산지 표시 포함)      | ItemMatiere
6    | 영양정보                                                                          | ItemIngredient
7    | 기능정보                                                                          | ItemSpec1
8    | 섭취량, 섭취방법 및 섭취 시 주의사항 및 부작용 가능성                             | ItemCaution
9    | 질병의 예방 및 치료를 위한 의약품이 아니라는 내용의 표현                          | ItemSpec2
10   | 유전자변형건강기능식                                                              | ItemGeneticallyMod
11   | 표시광고 사전심의필                                                               | ItemSpecialFood
12   | 수입식품에 해당하는 경우 "건강기능식품에 관한 법률에 따른 수입신고를 필함"의 문구 | ItemImport
13   | 소비자상담 관련 전화번호                                                          | ItemAsTel

### [g16] 영상가전 필수 항목
순번 | 항목명                      | 필드명
---- | --------------------------- | ----
1    | 품명 및 모델명              | ItemPartnerCode
2    | 정격전압, 소비전력                        | ItemSpec1
3    | 에너지소비효율등급 (에너지이용합리화법 상 의무대상상품에 한함)                    | ItemSpec2
4    | KC 인증 필 유무 (전기용품안전관리법 상 안전인증대상전기용품, 안전확인대상전기용품, 공급자적합성확인대상전기용품에 한함)             | ItemWarranty
5    | 동일모델의 출시년월                      | ItemEqualmodelLaunchdt
6    | 제조자                        | ItemMaker
7    | 수입품의 경우 수입자를 함께 표기 (병행수입의 경우 병행수입 여부로 대체 가능)                      | ItemImporter
8    | 제조국                      | ItemOrigin
9    | 크기 (형태포함)                        | ItemSizes
10   | 화면사양 (크기, 해상도, 화면비율 등)               | ItemVolume
11   | 품질보증기준              | ItemQualityAssurance
12   | AS 책임자                   | ItemAsName
13   | AS 전화번호                 | ItemAsTel

### [g17] 계절가전 필수 항목
순번 | 항목명                      | 필드명
---- | --------------------------- | ----
1    | 품명 및 모델명              | ItemGoodscd
2    | 정격전압, 소비전력                        | ItemSpec1
3    | 에너지소비효울등급 (에너지이용합리화법 상 의무대상상품에 한함)                    | ItemSpec2
4    | KC 인증 필 유무 (전기용품안전관리법 상 안전인증대상전기용품, 안전확인대상전기용품, 공급자적합성확인대상전기용품에 한함)             | ItemWarranty
5    | 동일모델의 출시년월                      | ItemEqualmodelLaunchdt
6    | 제조자                        | ItemMaker
7    | 수입품의 경우 수입자를 함께 표기 (병행수입의 경우 병행수입 여부로 대체 가능)                      | ItemImporter
8    | 제조국                      | ItemOrigin
9    | 크기 (형태 및 실외기 포함)                        | ItemSizes
10   | 냉난방면적               | ItemVolume
11   | 추가설치비용              | ItemServiceLife
12   | 품질보증기준                   | ItemQualityAssurance
13   | AS 책임자                 | ItemASName
14   | AS 전화번호                 | ItemASTel

###[g18] 사무용기기 필수 항목
순번 | 항목명                      | 필드명
---- | --------------------------- | ----
1    | 품명 및 모델명              | ItemGoodscd
2    | 정격전압, 소비전력                        | ItemSpec1
3    | 에너지소비효율등급 (에너지이용합리화법 상 의무대상상품에 한함)                    | ItemSpec2
4    | KC 인증 필 유무 (전파법 상 인증대상상품에 한함, MIC 인증 필 혼용 가능)             | ItemWarranty
5    | 동일모델의 출시년월                      | ItemEqualmodelLaunchdt
6    | 제조자                        | ItemMaker
7    | 수입품의 경우 수입자를 함께 표기 (병행수입의 경우 병행수입 여부로 대체 가능)                      | ItemImporter
8    | 제조국                      | ItemOrigin
9    | 크기, 무게 (무게는 노트북에 한함)                        | ItemSizes
10   | 주요 사양 (컴퓨터와 노트북의 경우 성능, 용량, 운영체제 포함여부 등 / 프린터의 경우 인쇄 속도 등)               | ItemVolume
11   | 품질보증기준              | ItemQualityAssurance
12   | AS 책임자                   | ItemAsName
13   | AS 전화번호                 | ItemAsTel

###[g19] 광학기기 필수 항목
순번 | 항목명                      | 필드명
---- | --------------------------- | ----
1    | 품명 및 모델명              | ItemGoodscd
2    | 동일모델의 출시년월                        | ItemEqualmodelLaunchdt
3    | KC인증필 (전파법 상 인증대상상품에 한함, MIC 인증 필 혼용 가능)                    | ItemWarranty
4    | 제조자             | ItemMaker
5    | 수입품의 경우 수입자를 함께 표기 (병행수입의 경우 병행수입 여부로 대체 가능)                      | ItemImporter
6    | 제조국                        | ItemOrigin
7    | 크기, 무게                      | ItemSizes
8    | 주요 사양                      | ItemVolume
9    | 품질보증기준                        | ItemQualityAssurance
12   | AS 책임자                   | ItemAsName
13   | AS 전화번호                 | ItemAsTel

###[g20] 소형전자 필수 항목
순번 | 항목명                      | 필드명
---- | --------------------------- | ----
1    | 품명 및 모델명              | ItemGoodscd
2    | 정격전압, 소비전력                        | ItemSpec1
3    | KC인증 필 유무 (전파법 상 인증대상상품에 한함, MIC 인증 필 혼용 가능)                    | ItemWarranty
4    | 동일모델의 출시년월             | ItemEqualmodelLaunchdt
5    | 제조자                      | ItemMaker
6    | 수입품의 경우 수입자를 함께 표기 (병행수입의 경우 병행수입 여부로 대체 가능)                        | ItemImporter
7    | 제조국                      | ItemOrigin
8    | 크기, 무게                      | ItemSizes
9    | 주요 사양                        | ItemVolume
10   | 품질보증기준              | ItemQualityAssurance
11   | AS 책임자                   | ItemAsName
12   | AS 전화번호                 | ItemAsTel

###[g21] 내비게이션 필수 항목
순번 | 항목명                      | 필드명
---- | --------------------------- | ----
1    | 품명 및 모델명              | ItemGoodscd
2    | 정격전압, 소비전력                        | ItemSpec1
3    | KC인증 필 유무 (전파법 상 인증대상상품에 한함, MIC 인증 필 혼용 가능)                    | ItemWarranty
4    | 동일모델의 출시년월             | ItemEqualmodelLaunchdt
5    | 제조자                      | ItemMaker
6    | 수입품의 경우 수입자를 함께 표기 (병행수입의 경우 병행수입 여부로 대체 가능)                        | ItemImporter
7    | 제조국                      | ItemOrigin
8    | 크기. 무게                      | ItemSizes
9    | 주요 사양                        | ItemVolume
10   | 앱 업데이트 비용 및 무상기간               | ItemServiceLife
11   | 품질보증기준              | ItemQualityAssurance
12   | AS 책임자                   | ItemAsName
13   | AS 전화번호                 | ItemAsTel

###[g22] 자동차용품 필수 항목
순번 | 항목명                      | 필드명
---- | --------------------------- | ----
1    | 품명 및 모델명              | ItemGoodscd
2    | 동일모델의 출시년월                        | ItemEqualmodelLaunchdt
3    | KC인증 필 유무 (전파법 상 인증대상상품에 한함, MIC 인증 필 혼용 가능)                    | ItemWarranty
4    | 제조자                      | ItemMaker
5    | 수입품의 경우 수입자를 함께 표기 (병행수입의 경우 병행수입 여부로 대체 가능)                        | ItemImporter
6    | 제조국                      | ItemOrigin
7    | 크기                      | ItemSizes
8    | 적용차종                        | ItemVolume
9    | 품질보증기준              | ItemQualityAssurance
10   | AS 책임자                   | ItemAsName
11   | AS 전화번호                 | ItemAsTel

###[g23] 의료기기 필수 항목
순번 | 항목명                      | 필드명
---- | --------------------------- | ----
1    | 품명 및 모델명              | ItemGoodscd
2    | 정격전압, 소비전력 (전기용품에 한함)                        | ItemSpec1
3    | 의료기기법상 허가·신고 번호 (허가·신고 대상 의료기기에 한함 및 광고사전심의필 유무)                   | ItemWarranty
4    | 동일모델의 출시년월             | ItemEqualmodelLaunchdt
5    | 제조자                      | ItemMaker
6    | 수입품의 경우 수입자를 함께 표기 (병행수입의 경우 병행수입 여부로 대체 가능)                        | ItemImporter
7    | 제조국                      | ItemOrigin
8    | 제품의 사용목적 및 사용방법                      | ItemUsages
9    | 취급시 주의사항                        | ItemCaution
10   | 품질보증기준              | ItemQualityAssurance
11   | AS 책임자                   | ItemAsName
12   | AS 전화번호                 | ItemAsTel

## 6-3. KC 안전인증 유형
내용                         | 상세여부
---------------------------- | --------
해당없음                     |
상세설명참조                 |
[생활용품]안전인증           | 입력
[생활용품]안전확인           | 입력
[생활용품]공급자적합성확인   |
[생활용품]어린이보호포장     | 입력
[어린이제품]안전인증         | 입력
[어린이제품]안전확인         | 입력
[어린이제품]공급자적합성확인 |
[전기용품]안전인증           | 입력
[전기용품]안전확인           | 입력
[전기용품]공급자적합성확인   |
[방송통신기자재]적합성평가   | 입력
[위해우려제품]자가검사번호   | 입력

# Etc

### End. 감사합니다 :)
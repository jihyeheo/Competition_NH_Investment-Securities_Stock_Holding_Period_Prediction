# Competition-NH_Investment-Securities_Stock_Holding_Period_Prediction [20211001 ~ 20211013]

## 데이터분석동아리 수DA쟁이 팀프로젝트: 최우철, 장민수, 진서영

## 문제
다양한 데이터를 활용하여 고객이 보유한 주식 종목 별 보유기간을 예측한다. 회귀분석을 이용하였다.

## 주어진 DATA
1. cus_info.csv : 고객 및 주거래계좌 정보<br>
[**columns**] act_id: 계좌 ID, sex_dit_cd: 성별, cus_age_stn_cd: 연령대, ivs_icn_cd: 투자성향, cus_aet_stn_cd: 자산구간
mrz_pdt_tp_sgm_cd: 주거래상품군, lsg_sgm_cd: Life Style, tco_cus_grd_cd: 서비스 등급, tot_ivs_te_sgm_cd: 총 투자기간
mrz_btp_dit_cd: 주거래업종구분<br>
2. stk_bnc_hist.csv : 국내주식 잔고이력<br>
[**columns**] act_id: 계좌 ID, bse_dt: 기준일자, iem_cd: 종목코드, bnc_qty: 잔고수량, tot_aet_amt: 잔고금액, stk_par_pr: 주당 액면가<br>
3. iem_info.csv : 종목정보<br>
[**columns**] iem_cd: 종목코드, iem_krl_nm: 종목한글명, btp_cfc_cd: 종목업종, mkt_pr_tal_scl_tp_cd: 시가총액 규모유형, stk_dit_cd: 시장구분<br>
4. stk_hld_train.csv : 16년 1월 ~ 20년 12월 사이 고객의 국내주식 거래가 종료된 건<br>
[**columns**] act_id: 계좌 ID, iem_cd: 종목코드, byn_dt: 매수일자, hold_d: 보유기간(일)<br>
5. stk_hld_test.csv : 20년 12월 이전에 매수하고 21년 이후에 고객이 전량 매도한 국내주식 보유기간 예측<br>
[**columns**] act_id: 계좌 ID, iem_cd: 종목코드, byn_dt: 매수 일자, hist_d: 과거 보유일, submit_id: 제출ID, hold_d: 보유기간(일)<br>

## 1) 1st meeting : 데이터 파악하기 [20211004]()
- baseline 따라하기
: LGBRegressor(max_depth=6, n_estimators=2000, learning_rate=0.01,num_leaves=31), 5-fold
- 상관 관계 분석(spearman)<br>
![image](https://user-images.githubusercontent.com/64202709/138924468-ac1b9c73-0dc2-422a-9619-ca5dc28dec24.png)
- 독립변수 간 다중 공산성 파악<br>
 분산팽창요인을 가지고 비교 -> cus_age_stn_cd, cus_aet_stn_cd, tco_cus_grd_cd, lsg_sgm_cd, mkt_pr_tal_scl_tp_cd, stk_dit_cd 제거<br> 
![image](https://user-images.githubusercontent.com/64202709/138924975-9507a1dd-d35b-44ee-b425-fb8db5de2e5c.png)

**편-안**
베이스라인 : 86
다중공산성 제거 후 베이스라인 : 83.09

## 2) 2nd meeting :

## 3) 3rd meeting


## 4) Final
[Presentation]()

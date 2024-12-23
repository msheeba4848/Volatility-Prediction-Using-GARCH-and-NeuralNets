## Volatility Prediction Models: Ethereum and Monero

### MODEL 1: Ethereum

This analysis explores a comprehensive comparison of statistical and machine learning models for financial time series forecasting, focusing on volatility prediction for Ethereum. The methodologies examined include both traditional statistical models and advanced neural network architectures.

#### Statistical Models

The statistical models implemented include:
- **GARCH(1,1)**
- **TARCH(1,1)**
- **EGARCH(1,1)**
- **GJR-GARCH(1,1,1)**

These were evaluated under constant mean specifications with both normal and Student’s t-distributions. The results demonstrated varied performance:
- **EGARCH(1,1)** with a Student’s t-distribution achieved the best RMSPE of 0.3324, outperforming GARCH(1,1) and ARCH variants.

#### Machine Learning Models

The machine learning approaches began with a baseline neural network achieving an RMSPE of 0.3272. Further improvements were noted with:
- **Single-layer LSTM**: Achieved an RMSPE of 0.2646 using a 14-day lookback window.
- **Bidirectional LSTMs**: Enhanced performance, achieving RMSPE values of 0.2229 (2-layer) and 0.4101 (3-layer) for univariate and multivariate features, respectively.

Additional enhancements included:
- **Conv1D and Dropout Layers**: Improved performance while managing overfitting challenges.
- **Hybrid Conv1D-Bidirectional LSTM**: Achieved an RMSPE of 0.3102, balancing complexity and accuracy.
- **Learning Rate Tuning**: Optimized bidirectional LSTMs, but increasing model complexity to four layers resulted in overfitting, with an RMSPE of 0.7242.

The multivariate LSTM model incorporated features like:
- High-low spreads (HL_sprd)
- Close-open spreads (CO_sprd)
- Volume
- Current volatility

This configuration provided significant insights but reached an RMSPE of 0.4101 for a 3-layer model.

#### Key Takeaways

- Deep learning models excel in capturing nonlinear dependencies but risk overfitting with increased complexity.
- Statistical models, particularly EGARCH and GJR-GARCH, offer robust baseline performance and interpretability.
- Combining statistical rigor with neural architectures may lead to more robust financial models.

### MODEL 2: Monero

This study evaluates volatility prediction for Monero, focusing on comparing traditional econometric models with deep learning architectures. The analysis underscores the importance of risk management, portfolio optimization, and trading strategies informed by volatility forecasts.

#### Traditional Models

The econometric models analyzed include:
- **TARCH**
- **GARCH**
- **EGARCH**

Key findings:
- **Bootstrap TARCH(1,1)** (Student’s t-distribution): RMSPE of 0.302.
- **EGARCH(1,1)** (Student’s t-distribution): RMSPE of 0.337.

While these models are robust and interpretable, their rigid assumptions about linearity and stationarity limit adaptability to dynamic market conditions.

#### Neural Network Models

Neural network architectures demonstrated superior performance:
- **Single-layer LSTM**: Achieved an RMSPE of 0.399 with a 14-day lookback window.
- **Multivariate 3-layer Bidirectional LSTM**: RMSPE improved to 0.275, highlighting its ability to model complex dependencies across features like price movements, volume, and spreads.

Feature engineering played a pivotal role, incorporating:
- High-low spreads (HL_sprd)
- Close-open spreads (CO_sprd)
- Log-transformed volume

Advanced configurations included:
- **Convolutional Layers**: Enhanced model refinement.
- **Hyperparameter Optimization**: Improved performance but required careful tuning to avoid overfitting.

#### Key Takeaways

- Traditional models remain valuable for their interpretability and efficiency.
- Neural networks offer unparalleled accuracy and flexibility but demand computational resources and fine-tuning.
- Hybrid approaches combining traditional and deep learning models may balance interpretability and predictive power.

---

## License

This project is licensed under an **All Rights Reserved** license. Unauthorized use, distribution, or modification of the code is strictly prohibited. For inquiries or permission requests, please contact [sm3924@georgetown.edu or msheeba00@gmail.com].

### Conclusion

This comparative analysis demonstrates the potential of neural networks, particularly LSTMs, to outperform traditional models in financial time series forecasting. Statistical models like EGARCH provide a robust baseline, while deep learning architectures capture intricate market dynamics. Future work could focus on hybrid frameworks, ensemble methods, and integrating exogenous variables to enhance volatility prediction models for both Ethereum and Monero.

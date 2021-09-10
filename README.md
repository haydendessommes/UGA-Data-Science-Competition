# UGA Data Science Competition




<!-- PROJECT SHIELDS -->




<!-- PROJECT LOGO -->
<br />

  <h3 align="center">UGA Inaugural Data Science Competition</h3>
    <h4 align="center">Sponsored by Wells Fargo</h4>





<!-- TABLE OF CONTENTS -->
<details open="open">
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
   <li><a href="#usage">Data</a></li>
    <li>
      <a href="#getting-started">Exploratory Data Analysis</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#roadmap">Roadmap</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#acknowledgements">Acknowledgements</a></li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
## About The Project

In order to apply for a loan, banks require individuals to provide things like proof of
income, proof of assets, and collateral. This is because it is not in the bank’s best interest to
loan money to people who are likely to default. However, even with ensuring that they only loan
money to the most responsible people, it is still not uncommon for people to default. If there was
a model that predicted whether someone would default based on data on their credit history,
banks could distribute money for loans more effectively. The goal of this project is to do just that,
build a model to predict whether or not a person will default on their loan based on their credit
history data.

## Data
The datasets consist of historical data from a hypothetical bank XYZ in the Southeastern US. We were given a test dataset (5,000 records), a training dataset (20,000 records), and a validation dataset (3,000 records), each of which contains 20 predictor variables and one response variable. The response variable is Default_ind, an indicator variable that equals 1 if the approved account defaulted, and equals 0 if not defaulted. The predictor variables and their descriptions are shown below:
* Total debt on all credit products
* Average debt on all credit cards over last 12 months
* Age (months) of first credit product
* Age (months) of first credit product currently in good standing
* Age (months) of first credit card
* Number of non-mortgage credit products past due in last 12 months
* Number of non-mortgage credit products past due in last 6 months
* Number of mortgages past due in last 6 months
* Total amount of money past due on all accounts
* Number of credit inquiries in last 12 months
* Number of credit card inquiries in last 24 months
* Number of credit cards opened in last 36 months
* Number of auto loans opened in last 36 months
* Utilization on all credit card accounts
* % of open credit products with >50% utilization
* Utilization of credit product with highest credit limit
* % of open credit cards with >50% utilization
* Indicator: 1 if applicant has an account with XYZ Bank; 0 otherwise
* Self-reported annual income
* Residence state (AL, FL, GA, LA, MS, NS, SC)



### Exploratory Data Analysis

The majority of applicants did not default on their loans. Of the 20,000 records in the training set, only 1,586 of them (7.93%) defaulted. This class imbalance will be addressed later on in the report. For the predictors, there are several different classes of variables in the dataset. Most of the variables are continuous. However there are a few countable numeric variables, an indicator variable, and a categorical variable. Figures showing the distributions for each predictor can be shown in the report contained in this repository. Most of the numeric variables appear to be normally distributed, and several are skewed to the right. The only categorical predictor variable is the state indicator, which we will convert into binary indicators for each state. Only 3 predictors contained missing variables, each between 7%-10% of the total number of records: uti_card_50plus_pct, rep_income, avg_card_debt. The variables were tested to be missing at random, so they were imputed from the existing data. The records were then tested for multicollinearity, and the following predictors contained problematically high VIF numbers and were removed: credit_age, card_age, mortgages_past_due_6_months_num, credit_past_due_amount, uti_card. 

More details regarding our EDA Process can be found in our report.






<!-- GETTING STARTED -->
## Logistic Regression Modelling

Now that we have our predictor variables ready, we decided to run a stepwise regression to make sure we were only including predictors that had a significant impact on the model. This narrowed down the number of predictors to 10. A chart containing the odds ratios for each variable are shown in the report. Results of the logistic regression are shown below:

Precision: 0.2192

Recall: 0.7107

Accuracy: 0.7738

F1 Score: 0.3351


### Prerequisites

This is an example of how to list things you need to use the software and how to install them.
* npm
  ```sh
  npm install npm@latest -g
  ```

### Installation

1. Get a free API Key at [https://example.com](https://example.com)
2. Clone the repo
   ```sh
   git clone https://github.com/your_username_/Project-Name.git
   ```
3. Install NPM packages
   ```sh
   npm install
   ```
4. Enter your API in `config.js`
   ```JS
   const API_KEY = 'ENTER YOUR API';
   ```



<!-- USAGE EXAMPLES -->
## Usage

Use this space to show useful examples of how a project can be used. Additional screenshots, code examples and demos work well in this space. You may also link to more resources.

_For more examples, please refer to the [Documentation](https://example.com)_



<!-- ROADMAP -->
## Roadmap

See the [open issues](https://github.com/othneildrew/Best-README-Template/issues) for a list of proposed features (and known issues).



<!-- CONTRIBUTING -->
## Contributing

Contributions are what make the open source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request



<!-- LICENSE -->
## License

Distributed under the MIT License. See `LICENSE` for more information.



<!-- CONTACT -->
## Contact

Your Name - [@your_twitter](https://twitter.com/your_username) - email@example.com

Project Link: [https://github.com/your_username/repo_name](https://github.com/your_username/repo_name)



<!-- ACKNOWLEDGEMENTS -->
## Acknowledgements
* [GitHub Emoji Cheat Sheet](https://www.webpagefx.com/tools/emoji-cheat-sheet)
* [Img Shields](https://shields.io)
* [Choose an Open Source License](https://choosealicense.com)
* [GitHub Pages](https://pages.github.com)
* [Animate.css](https://daneden.github.io/animate.css)
* [Loaders.css](https://connoratherton.com/loaders)
* [Slick Carousel](https://kenwheeler.github.io/slick)
* [Smooth Scroll](https://github.com/cferdinandi/smooth-scroll)
* [Sticky Kit](http://leafo.net/sticky-kit)
* [JVectorMap](http://jvectormap.com)
* [Font Awesome](https://fontawesome.com)





<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/othneildrew/Best-README-Template.svg?style=for-the-badge
[contributors-url]: https://github.com/othneildrew/Best-README-Template/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/othneildrew/Best-README-Template.svg?style=for-the-badge
[forks-url]: https://github.com/othneildrew/Best-README-Template/network/members
[stars-shield]: https://img.shields.io/github/stars/othneildrew/Best-README-Template.svg?style=for-the-badge
[stars-url]: https://github.com/othneildrew/Best-README-Template/stargazers
[issues-shield]: https://img.shields.io/github/issues/othneildrew/Best-README-Template.svg?style=for-the-badge
[issues-url]: https://github.com/othneildrew/Best-README-Template/issues
[license-shield]: https://img.shields.io/github/license/othneildrew/Best-README-Template.svg?style=for-the-badge
[license-url]: https://github.com/othneildrew/Best-README-Template/blob/master/LICENSE.txt
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://linkedin.com/in/othneildrew
[product-screenshot]: images/screenshot.png
